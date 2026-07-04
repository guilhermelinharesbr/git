# Estudo de Git

---


#### Sumário
- [Definição](#definição)
- [Comandos](#comandos)
- [git --help](#git---help)
- [git --version](#git---version)
- [git init](#git-init)
- [git status](#git-status)
- [git add](#git-add)



---


### Definição 

O Git é um sistema de controle de versão distribuído e de código aberto. Ele rastreia e gerencia as alterações feitas em arquivos ao longo do tempo, permitindo que desenvolvedores salvem diferentes versões de um projeto, colaborem simultaneamente sem sobrescrever o trabalho alheio e voltem facilmente a um estado funcional caso ocorram erros.


---

### Comandos

Abaixo temos comandos Git em uma ordem que facilita a consulta ou aprendizado.

---

#### git --help

Mostra as opções do comando git.

Ex:  
**git push --help
git help push** 

---

#### git --version

Mostra a versão do Git.

---

#### git init

Inicializa repositório. 
Quando se faz isso ele cria um diretório oculto de nome .git.

Ex:  
**git init** -> torna o diretório atual um respositório local do git e cria um diretório oculto de nome .git dentro dele.

Ex2:  
**git init** _nome-repositorio_ -> cria no diretório atual um diretório chamado nome-repositorio e dentro dele cria um diretório oculto de nome .git.

---

#### git status

Verifica se alguma mudança foi feita no branch atual.

---

#### git add

Adiciona arquivos ao versionamento, no caso para a área de stage.

Ex:  
**git add .** -> Adiciona todos os arquivos.

Ex2:  
**git add** _nome_arquivo_
**git add imagem.png** -> Se quiser adicionar apenas um arquivo.

Ex3:  
**git add -A** -> Adiciona todos os arquivos de maneira mais completa, pegando tudo (novos + modificados + deletados).

Ex4:  
**git add .\*css** -> Adiciona para o stage todos os arquivos .css.

---
