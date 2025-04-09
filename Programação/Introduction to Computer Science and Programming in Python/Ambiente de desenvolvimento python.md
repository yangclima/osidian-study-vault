# Pyenv
Pyenv é um gerenciador de versões python e pode ser usado para gerenciar e alternar entre versões do python, para instalá-lo usamos:
```powershell
Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
```
Para instalar uma versão python usamos:
```powershell
pyenv install <version>
```
Para definirmos uma versão global do python usamos:
```powershell
pyenv global <version>
```
Para definirmos versões locais do python, ou seja, uma versão para uma pasta específica usamos o seguinte:
```powershell
pyenv local <version>
```
Para visualizar as versões python instaladas usamos:
```powershell
pyenv versions
```
# Poetry
Poetry é um moderno gerenciador de pacotes e dependências python, que pode ser instalado através do `pip`, da seguinte forma:
```powershell
pip install poetry
```
## Configurando o *poetry*
Podemos listar as configurações do *poetry* usando o seguinte comando:
```powershell
poetry config --list
```
Uma alteração muito comum das configurações e que serve para que as pastas de ambientes virtuais sejam criadas sempre dentro da pasta do projeto é feita da seguinte forma:
```powershell
poetry config virtualenvs.in-project true
```
O comando básico para mudar uma configuração do gerenciador é:
```powershell
poetry config <configuracao> <valor>
```
## Criando um projeto
Um projeto pode ser criado com *poetry* a partir do seguinte comando:
```powershell
poetry new <"nome do projeto">
```
Para criar um [[Criar ambiente virtual|ambiente virtual]] usando o *poetry* usamos o seguinte:
```powershell
poetry env use python
```
Para instalar um pacote usamos:
```powershell
poetry add <"nome do pacote">
```