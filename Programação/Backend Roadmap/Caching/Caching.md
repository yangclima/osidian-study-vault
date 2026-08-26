# O que é Caching?
Caching é o processo de armazenar cópias de dados em uma camada de acesso rápido (geralmente em memória) para reduzir a latência, acelerar a entrega de informações e diminuir a carga computacional nos sistemas de origem (banco de dados ou APIs). Neste contexto, chamamos de **Cache Hit** quando a aplicação solicita um dado e o encontra no cache, e **Cache Miss** quando o dado não está presente ou já expirou.

# Níveis e Aplicações de Cache
O cache é aplicado em diferentes camadas da arquitetura:

- **Hardware:** Organizado em hierarquia de velocidade e custo: CPU (L1, L2, L3) → RAM → Disco (SSD/NVMe).
- **Client-Side (Navegadores):** Evita downloads repetidos de arquivos estáticos. É controlado via **Headers HTTP** (como `Cache-Control`, `max-age` e `ETag`), e não simplesmente por "TTL".
- **Network (DNS e CDNs):** Servidores DNS fazem cache de resolução de domínios; CDNs distribuem dados estáticos globalmente para deixá-los mais próximos do usuário final.
- **Server-Side:** Reduz a carga no banco de dados. Pode ser **Local** (em memória no próprio servidor da aplicação) ou **Distribuído** (sistemas dedicados como Redis e Memcached).

# Desafios do Caching
A introdução de um sistema de cache aumenta a complexidade da arquitetura, trazendo desafios como:

- **Inconsistência de Dados:** O risco de o usuário visualizar dados antigos (stale data) se a fonte original for alterada e o cache não for notificado.
- **Cache Stampede (Thundering Herd):** Problema crítico onde uma chave muito acessada expira, fazendo com que milhares de requisições atinjam o banco de dados simultaneamente antes que o cache seja repopulado.
- **Invalidação de Cache:** A dificuldade de saber _quando_ limpar os dados. Pode ser feita passivamente (via TTL - Time To Live) ou ativamente (via eventos/código quando o dado muda no BD).
# Políticas de Eviction (Descarte)
Como a memória de cache é limitada, é necessário definir regras para liberar espaço quando o limite é atingido. As principais são:

- **LRU (Least Recently Used):** Descarta o registro que não é acessado há mais tempo. (Padrão mais comum).
- **MRU (Most Recently Used):** Descarta o registro acessado mais recentemente.
- **LFU (Least Frequently Used):** Descarta o registro com o menor número total de acessos.
- **FIFO (First In, First Out):** Descarta o registro mais antigo (o primeiro que foi salvo).
- **LIFO (Last In, First Out):** Descarta o registro mais novo.
- **RR (Random Replacement):** Descarta um registro aleatoriamente.

# Estratégias de Cache
Para implementar cache em uma aplicação, existem diferentes padrões de leitura e escrita (algumas dessas interações arquiteturais são ilustradas no diagrama).

![[ber_012.png]]

# Padrões de Leitura (Read Strategies):

- **Cache-Aside (Lazy Loading):** A aplicação verifica o cache primeiro. Se houver falha (miss), a aplicação busca no banco, salva no cache e retorna.
    - _Vantagens:_ Resiliente (se o cache cair, o BD assume as leituras).
    - _Desvantagens:_ A primeira leitura sempre sofre penalidade de latência; risco de dados desatualizados.
    
- **Read-Through:** A aplicação pede o dado ao cache. Em caso de miss, o próprio provedor de cache busca no BD e se atualiza.
	- _Vantagens:_ Código da aplicação fica mais limpo e simples.
    - _Desvantagens:_ Requer integração direta (forte acoplamento) entre o cache e o banco de dados.
    
- **Refresh-Ahead:** O cache analisa padrões e atualiza os dados em background proativamente, _antes_ que eles expirem.
    - _Vantagens:_ Latência de leitura quase zero (altíssimo _hit rate_).
    - _Desvantagens:_ Altamente complexo de configurar; gasta processamento atualizando dados que podem não ser lidos.

# Padrões de Escrita (Write Strategies):

- **Write-Through:** A aplicação escreve a atualização no cache e no BD de forma síncrona.
    - _Vantagens:_ Forte consistência (dados sempre atualizados).
    - _Desvantagens:_ Maior latência na escrita, pois depende de duas operações.
    
- **Write-Around:** A aplicação escreve diretamente no BD, ignorando o cache.
    - _Vantagens:_ Evita poluir o cache com dados pesados que podem não ser lidos em seguida.
    - _Desvantagens:_ A leitura subsequente sempre resultará em um _cache miss_.
        
- **Write-Back (Write-Behind):** A aplicação escreve apenas no cache e finaliza a requisição. O cache sincroniza com o BD em background (assincronamente).
    - _Vantagens:_ Performance extrema para escrita; ótimo para sistemas com alto volume de gravação.
    - _Desvantagens:_ Baixa confiabilidade (se a energia ou o cache cair antes da sincronização, há perda definitiva de dados).