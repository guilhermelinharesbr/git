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
- [git commit](#git-commit)
- [git push](#git-push)
- [git pull](#git-pull)
- [git restore](#git-restore)
- [git branch](#git-branch)
- [git clone](#git-clone)
- [git fetch](#git-fetch)



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

#### git commit

Salva as alterações de código.

Ex:  
**git commit -a -m "Criacao do arquivo HTML"** -> faz o commit, a opção **-a** serve para adicionar automaticamente para arquivos já rastreados pelo Git. A opção -a evita ter que rodar um _git add nomearquivo.txt_ e depois _git commit -m "Criacao do arquivo .txt"_
Inclui automaticamente arquivos modificados. Inclui arquivos deletados. NÃO inclui arquivos novos (não rastreados). Já a opção -m permite colocar a mensagem do commit direto na linha de comando.

Ex2:  
**git commit -m "Mudanca no Readme\.md"** 

Ex3:  
**git commit --amend -m "Adicionando novo arquivo"** -> Altera o último commit feito. O **--amend** vem do inglês corrigir/emendar/alterar. Neste caso ele pega o último commit e cria um novo commit no lugar dele, usa a nova mensagem "Adicionando novo arquivo", inclui tudo que está atualmente no stage (git add) e apaga o commit anterior (na prática, ele deixa de existir no histórico).

---

#### git push

Envia atualizações para o repositório remoto.

Ex:  
**git push -u origin main** -> faz o envio da sua branch main para o repositório remoto (origin) e ainda define ela como padrão. A opção **-u** significa **--set-upstream** (define rastreamento padrão), ao usar a opção _-u_ neste momento evita-se ter que ficar digitando _git push origin main_ apenas, _git push_ e _git pull_, pois o Git já sabe que: main → origin/main.

Ex2:  
**git push origin main**

Ex3:  
**git push origin novo-botao**

Ex4:  
**git push origin main --force** -> Faz um push forçado da branch main para o repositório remoto. Normalmente, o Git só permite push se não houver conflito de histórico, mas com **--force**, será ignorado o histórico remoto e substituído pelo histórico local. É utilizado quando se quer sincornizar os commits do ambiente local com o remoto.

Ex5:  
**git push origin v2026.04** -> Manda apenas a tag de nome v2026.04 para o GitHub.

Ex6:  
**git push origin --delete v2026.04** -> Deleta a tag de nome v2026.04 do GitHub.

---

#### git pull

Busca e integre-se a outro repositório ou em uma branch local. Incorpora alterações de um repositório remoto na branch atual.

 Ex:  
```bash
$ git pull
Updating 957f6ac..0df5f5b
Fast-forward
```
O _Fast-forward_ é a forma mais limpa e direta que o Git tem de atualizar o seu código. Ele acontece quando a branch que você está puxando (a remota) tem commits novos, mas a sua branch local não tem nenhum commit novo feito por você.
Basicamente, o Git percebe que não há nenhum conflito para resolver e nenhuma história para juntar. A única coisa que ele precisa fazer é "mover o ponteiro" da sua branch local para frente, apontando para o commit mais recente.
Para entender melhor o que aconteceu na sua tela:
_Updating 957f6ac..0df5f5b_: O Git está dizendo que a sua branch local estava no commit 957f6ac e agora foi atualizada para o commit 0df5f5b.
_Fast-forward_: Significa que essa atualização foi feita sem a necessidade de criar um novo "commit de merge". O histórico continuou uma linha reta perfeita.

---

#### git restore

Restaurar arquivos da árvore de trabalho.

Ex:  
**git restore index.html** -> Descarta as alterações feitas no arquivo index.html, voltando ele para o estado do último commit.

---

#### git branch

Lista todas as ramificações existentes, além de mostrar em qual branch você está.

Ex:  
**git branch** -> Lista as branches existente e a que você está usando.

Ex2:  
**git branch -M main** -> A opção **-M** força a renomeação, mesmo que já exista uma branch com esse nome. Se usar **-m** renomearia apenas se não existir uma branch de nome main.  
**-m**  = rename (safe)  
**-M**  = rename (force)

Ex3:  
**git branch novas-cores** -> Cria uma branch de nome novas-cores.

Ex4:  
**git branch -d novas-cores** -> Deleta a branch de nome novas-cores.

---

#### git clone

Clona um repositório.

Ex:  
**git clone** https://github.com/guilhermelinharesbr/markdown.git

Ex2:  
**git clone** https://github.com/guilhermelinharesbr/tutorial_git.git testeclone -> Clona o projeto e joga em um pasta chamada testeclone.

Ex3:  
**git clone** git@github.com:guilhermelinharesbr/markdown.git -> Clona o repositório usando SSH ao invés de HTTPS.

---

#### git fetch

Baixa objetos e referências de outro repositório.
Obtenha branches e/ou tags (coletivamente, "refs") de um ou mais repositórios, juntamente com os objetos necessários para completar seus históricos.
Usado basicamente para alinhar os históricos do repositório local com o remoto, para assim, decidir se precisa fazer um _git pull_ antes de fazer um _git push_.

Obs: O _git fetch_ pode ser usado para fazer o rebase de uma branch em vez de fazer o merge. Fetch e Rebase é melhor para manter o histórico do desenvolvimento.

Ex:  
**git fetch**

Ex2:  
**git fetch origin pull/ID/head:BRANCH** -> Cria uma branch com os commits do pull request.

---