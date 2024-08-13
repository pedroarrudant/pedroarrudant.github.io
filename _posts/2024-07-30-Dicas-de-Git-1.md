---
layout: single
title: Dicas de Git 1 - Squash Commits
author: Pedro Arruda
parent: home
header:
  image: "/images/miniatura-git.png"
  caption: "Dicas de Git #1"
  teaser: "/images/miniatura-git.png"
---
# Artigo
Alguma vez você já ficou irritado com o fato de precisar fazer um *cherry-pick* de uma branch para outra, e se deparar com esse cenário:

```bash
$ git log --oneline
f54530a (HEAD -> master) fix: Corrigindo mais informacoes ao arquivo
19dc69d fix: Corrigindo informacoes ao arquivo
969e9bf feat: Adicionando informacoes ao arquivo
bf1327d feat: criando repo
```

Como boa prática vc sempre deve comitar suas alterações sempre que possível, mas no minímo ao fim do dia. 

Para que vc não fique com um excesso de commits a serem levados da sua branch feature para uma branch fixa vc pode usar o squash para juntar todos os caras em um só.

## Tá, legal. Mas o que eu faço?

Para resolver esse problema vamos juntar os commits em um só, uma vez que a sua task era somente uma implementação de um arquivo e não todas essas correções que vc fez no meio do caminho.

> Se vc consegue dar um commit só e já resolver o problema esse artigo não é pra vc, é para humanos normais.

Primeiro vc precisa aglutinar os commits em um só usando o *git rebase* passando como referencia a quantidade de commits a serem unidos:

```bash
git rebase -i HEAD~<quantidade de commits>
```

Para o caso acima o comando fica assim:

```bash
git rebase -i HEAD~3
```

Ao fazer isso será aberto um arquivo de texto no vim (sim o vim!) e lá vc deverá alterar o commit que vc quer aglutinar, sendo eles marcados com a tag *squash* e o commit final com a tag *pick*.

```bash
pick 969e9bf feat: Adicionando informacoes ao arquivo
squash 19dc69d fix: Corrigindo informacoes ao arquivo
squash f54530a fix: Corrigindo mais informacoes ao arquivo

# Rebase bf1327d..f54530a onto bf1327d (3 commands)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
#                    opens the editor
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
#         create a merge commit using the original merge commit's
#         message (or the oneline, if no original merge commit was
#         specified); use -c <commit> to reword the commit message
# u, update-ref <ref> = track a placeholder for the <ref> to be updated
#                       to this position in the new commits. The <ref> is
#                       updated at the end of the rebase
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
```

Um segundo arquivo será aberto perguntando se vc deseja adicionar alguma mensagem adicional de commit, se não quiser é só salvar e seguir em frente.

> Tome cuidado para não ficar preso para sempre no VIM

```bash
pick 969e9bf feat: Adicionando informacoes ao arquivo
# This is a combination of 3 commits.
# This is the 1st commit message:

feat: Adicionando informacoes ao arquivo

# This is the commit message #2:

fix: Corrigindo informacoes ao arquivo

# This is the commit message #3:

fix: Corrigindo mais informacoes ao arquivo

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Tue Jul 30 17:14:42 2024 -0300
#
# interactive rebase in progress; onto bf1327d
# Last commands done (3 commands done):
#    squash 19dc69d fix: Corrigindo informacoes ao arquivo
#    squash f54530a fix: Corrigindo mais informacoes ao arquivo
# No commands remaining.
# You are currently rebasing branch 'master' on 'bf1327d'.
#
# Changes to be committed:
#       modified:   ArquivoComDados.txt
#
# This is a combination of 3 commits.
# This is the 1st commit message:

feat: Adicionando informacoes ao arquivo

# This is the commit message #2:

fix: Corrigindo informacoes ao arquivo

# This is the commit message #3:

fix: Corrigindo mais informacoes ao arquivo

# Please enter the commit message for your changes. Lines starting

```

Saindo do vim, vc terá o seguinte retorno ao rodar o comando *git log --oneline*:

```bash
$ git log --oneline
8ef96ee (HEAD -> master) feat: Adicionando informacoes ao arquivo
bf1327d feat: criando repo
```

> Para enviar para o repositório remoto vc precisará usar o comando de force no push, uma vez que o commit local difere do remoto. O comando exato é o *git push origin BRANCH-REMOTA --force*

Por hoje é isso, see ya.

![brazil_meme.gif]({{ site.baseurl }}/images/brazil-dancing-meme.gif)