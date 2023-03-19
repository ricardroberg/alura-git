https://git-school.github.io/visualizing-git/

1 - cria pasta
ex: mkdir servidor (D:/ALURA/GIT_GITHUB/servidor/)
2 - executar na pasta o comando
& git init --bare
3 - copia o caminho dessa pasta

4 - na pasta do seu projeto(D:/ALURA/GIT_GITHUB/ricard/), altere o repositorio remoto
ex: git remote add local D:/ALURA/GIT_GITHUB/servidor/ (local = nome do repositorio / e o caminho para o local)
pode-se adicionar varios repositorios
$ git remote -v
local D:/ALURA/GIT_GITHUB/servidor/ (fetch)
local D:/ALURA/GIT_GITHUB/servidor/ (push)

usando o repositorio remoto em outro projeto D:/ALURA/GIT_GITHUB/unforged
$ git clone /d/ALURA/GIT_GITHUB/servidor/ projeto (clonando o repositorio para um novo repositorio com o nome de 'projeto')

renomear repositorio local
git remote rename origin local

executar da branch atual
git merge branch_que_vai_juntar
(merge não preserva os logs da branch)

juntando as branchs mantendo os logs
git rebase branch_que_vai_juntar

==================================================
Vimos como é simples resolver conflitos identificados pelo Git ao tentar realizar o merge.
Agora, gere um conflito e, ao invés de utilizar o merge, utilize o rebase para atualizar o master:
Vá para a branch titulo
Commite algo
Vá para a branch master, commite uma alteração na mesma linha
Execute git rebase titulo
Veja a saída do Git e utilize as informações que ela te der para, após corrigir o conflito, continuar o rebase.
==================================================

MANIPULANDO VERSÕES (CTRL + Z)

git checkout -- <file_name> restore unstaged file
git restore --staged <file> to unstage (NOVO)
git reset HEAD <file> to unstage to HEAD (ANTIGO)
git revert <hash> create a commit undoing commit

git stash or git stash <file_name> to save modification for late use
git stash list to show stashed
git stash apply <#> para restaurar o stash
git stash drop <#> para remove-la da lista
git stash pop <#> restaura stash e remove da lista

DETACHED HEAD
git checkout para um commit anterior
para manter as alterações a partir desse commit deve-se criar uma nova branch para depois dar um merge ou
rebase na master

git checkout <branch_master> para retornar o HEAD

git log -n <#> mostra os últimos # commits
git log -p mostra todas as alterações feitas em cada commit
git log --online mostra os commits de forma reduzida, 1 por linha

git diff mostra o que foi alterado e não staged
git diff <hash>.. todas as diferenças do commit (hash) até o momento.

TAGS E RELEASES
git tag -a v0.1.0 -m "Lançando a primeira versão (BETA) da aplicação de cursos" (v0.1.0 nome qualquer)
