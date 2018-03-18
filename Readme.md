# Git
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

Se vc tiver comitado errado existem comandos para desfazer isso,
para isso existe o git reset, existem 3 tipos dele
git reset --soft --mixed --hard hash-do-commit, 
esses tipos só podem ser usados um de cada vez.

-O soft mata o commit, e o arquivo volta pro staged com as mesmas modificaçoes
-O mixed mata tambem, e retorna os arquivos pro modified, ou seja
os arquivos ainda possuem as modificaçoes
-O hard mata o commit junto com todas as mudanças dos arquivos. CUIDADO!

teste de email: [Kelven Live](dmytresksn@hotmail.com) 
ou 
[Kelven Gmail](dmytres@gmail.com)

### BRANCHS

Para criar um novo branch e ir para ele, use: git checkout -b nome-da-branch

Liste todas as branchs diponiveis com: git branch

Delete uma branch com: git branch -D nome-da-branch

### MERGE e Rebase

O rebase junta os branchs sem criar uma arvore mas alterando a ordem dos commits
Use-o com: git rebase nome-da-branch
assim se estiver na master juntara a
branch dada com a master.

O merge junta as branchs criando uma arvore e commits extras para a junçao acontecer
Use-o com: git merge nome-da-branch
Isso juntara a master com a branch dada.

#Github

Estando seu git local conectado com algum repositorio do Github, use o comando
para upar os commits feitos com: git push origin master
Sendo origin o branch do Hub e Master o local do Git

==Cuidado ao modificar o historico de commits local, ja tendo feito um push deles antes,
ocorrerá um conflito de historico, que pode ser resolvido com: git push -f origin master

