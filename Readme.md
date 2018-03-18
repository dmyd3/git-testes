# <b>Git</b>
## Aprendendo a usar o Git

Arquivo teste da aula de Git - aula 8
para salvar aperte esc e escreva :wq
w - escrever
q - sair

Para adcionar o arquivo usar o codigo: git add nome-do-arquivo

Para checar o status dos arquivos dentro do git usar: git status

Para salvar os arquivos e criar uma versar usar o: git commit
na pasta que vc quer usar
para adcionar comentarios de versao usar o parametro -m "comentario"
Exemplo: git commit -m "Meus comentarios dessa versao"

Para checar os commits feitos e seus comentarios, usar: git log

Para ver as diferenças de arquivos nao adcionados ainda(nao staged),
usar: git diff. MUITO IMPORTANTE
Para desfazer essas mudanças mostradas pelo DIFF usar: git checkout arquivo

Se o arquivo tiver sido adicionado e entrado no estado staged,
use: git reset HEAD arquivo. Para voltar ele pro estado unstaged
## Desfazendo de commits

Se vc tiver comitado errado existem comandos para desfazer isso,
para isso existe o git reset, existem 3 tipos dele
git reset --soft --mixed --hard hash-do-commit, 
esses tipos só podem ser usados um de cada vez.

-O soft mata o commit, e o arquivo volta pro staged com as mesmas modificaçoes
-O mixed mata tambem, e retorna os arquivos pro modified, ou seja
os arquivos ainda possuem as modificaçoes
-O hard mata o commit junto com todas as mudanças dos arquivos. CUIDADO!

Outra opçao para o reset é o revert, ele nao apaga os commits feitos, mas por
outro lado ele cria um novo commit igual a commit anterior, desfazendo o git
que nao deveria ter sido feito, mas deixando ele no historico pra ser visualizado
em outro momento se o usuário quiser, 
use ele com: git revert codigo-do-commit-mostrado-no-log
por exemplo: git revert 5ca46cs6c78as9c

teste de email: [Kelven Live](dmytresksn@hotmail.com) 
ou 
[Kelven Gmail](dmytres@gmail.com)

Para salvar atalhos de comandos do git use por exemplo:
git config --global alias.s status
assim o usuario poderá usar o comando git status como git s

Liste todos os atalhos com o comando: git config --get-regexp alias
ou com: gif config --list | grep alias

Apague atalhos que serao mais usados com o parametro --unset
exemplo: git config --global --unset alias.atalhos-setado

## Git Stash

O git Stash salva as mudanças realizadas em arquivos salvos que nao foram adicionadas
e comitadas ainda, para o usuario por exemplo criar novas branches sem as diferenças nao adicionadas e poder aplica-las depois, alguns comandos úteis sao:
git stash  *#armazena as diferenças
git stash apply *#aplica as diferenças de volta nos arquivos para poder edita-las
git stash list *#lista diferenças salvas
git stash clear *#limpa tais diferenças armazenadas

## Branches

Para criar um novo branch e ir para ele, use: git checkout -b nome-da-branch

Liste todas as branchs diponiveis com: git branch

Delete uma branch com: git branch -D nome-da-branch

Exiba informaçoes gráficas sobre os branches no log com: git log --graph
## Merge e Rebase

O rebase junta os branchs sem criar uma arvore mas alterando a ordem dos commits
Use-o com: git rebase nome-da-branch
assim se estiver na master juntara a
branch dada com a master.

O merge junta as branchs criando uma arvore e commits extras para a junçao acontecer
Use-o com: git merge nome-da-branch
Isso juntara a master com a branch dada.

# **Github**

Estando seu git local conectado com algum repositorio do Github, use o comando
para upar os commits feitos com: git push origin master
Sendo origin o branch do Hub e Master o local do Git

==Cuidado ao modificar o historico de commits local, ja tendo feito um push deles antes,
ocorrerá um conflito de historico, que pode ser resolvido com: git push -f origin master

O arquivo .gitignore pode ser usado para indicar quais arquivos o git nao deve
rastrear, ignorando formatos com asteristico.formato
ou arquivos especificos o nome dele escrito.

#### Tags

Tags sao usadas para versionar o seu projeto, para criar uma tag no git use:
git tag -a versao -m "Comentarios da versao"
por exemplo: git tag -a 1.0.1 -m "Arquivo X Atualizado"

Depois disso upe sua versao com: git push origin master --tags

Apagar tags no git é simples, use: git tag -d tag-a-apagar
Exemplo: git tag -d 1.0.0

## Desfazendo de Tags e Branches no Hub

Deletar tags e branches upadas é um processo rápido, ambas usam o seguinte
padrao de comando:
git push origin :tag-a-apagar
git push origin :branch-a-apagar

