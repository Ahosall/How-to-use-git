# Como usar o GIT no CMD(ou Prompt de Comandos).
Este markdown foi feito no intuito de ensinar os comandos básicos do git.

## CMD

1. Primeiro de tudo abra o CMD. `WIN` + `R`, ou pesquisando no menu do Windows.

2. Vá para pasta do seu projeto.
	```cmd
	C:\users\Ahosall> cd \Workspace\hello-world
	```
## GIT

### O que é GIT?

Em 2005, Linus Torvalds (o homem conhecido por criar o núcleo, ou kernel, do SO Linux) desenvolveu o GIT, que desde então tem sido ativamente mantido por Junio ​​Hamano, um engenheiro de software japonês.

Atualmente, o GIT é um dos mais famosos sistemas de controle de versão de código aberto e milhões de projetos no mundo inteiro o utilizam para seu controle de versão (incluindo projetos comerciais e de código aberto).

O Git é totalmente grátis e pode ser instalado em Mac, Linux, Windows e Solaris diretamente do site oficial . Algumas das características essenciais do GIT são:

1. Um sistema de controle de versão distribuído, o GIT segue uma abordagem peer to peer, contrário de outros como o Subversion (SVN) que segue um modelo baseado em cliente-servidor.

2. GIT permite aos desenvolvedores ter uma infinidade de ramos de código completamente independente. Criação, exclusão e fusão desses ramos é simples e não leva tempo.

3. No GIT, todas as operações são atômicas. Isso significa que uma ação pode ter sucesso ou falhar (sem fazer nenhuma alteração). Isso é importante porque em alguns sistemas de controle de versão (como o CVS) onde as operações não são atômicas, se uma operação de repositório é suspensa, ela pode deixar o repositório em um estado instável.

4. No GIT, tudo é armazenado dentro da pasta .git. Isso não é o mesmo em outros VCS como SVN e CVS onde os metadadados de arquivos são armazenados em pastas ocultas (por exemplo, .cvs, .svn, etc.)

5. GIT usa um modelo de dados que ajuda a garantir a integridade criptográfica de qualquer coisa presente dentro de um repositório. Cada vez que um arquivo é adicionado ou um commit é feito, suas somas de verificação são geradas. Da mesma forma, eles são recuperados através de suas somas de verificação também.

6. Outra característica presente no GIT é sua área de teste ou índice. Na área de preparação, os desenvolvedores podem formatar commits e receber feedback ​​antes de aplicá-los.

O GIT é consideravelmente simples de usar. Para começar, você pode criar um repositório ou conferir um já existente. Após a instalação, um simples git-init irá deixar tudo pronto. Da mesma maneira, o comando git clone pode criar uma cópia de um repositório local para um usuário.

Para iniciar um repositório no GIT você irá precisar executar este comando:
```cmd
C:\users\Ahosall\Workspace\hello-world> git init
```

Depois de já ter feito isso, verifique se a pasta `.git` foi criada.
```cmd
C:\users\Ahosall\Workspace\hello-world> DIR .
2021-03-28  13:28 PM <DIR>                  .git/
2021-03-28  13:28 PM <DIR>                  index.html
2021-03-28  13:28 PM <DIR>                  assets/
                                    1 Arquivo(s)
                                    2 Pasta(s)
```

A pasta `.git` foi criada. Agora execute o `git status` para ver as modificações.:
```cmd
C:\users\Ahosall\Workspace\hello-world> git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	index.html
	assets/

nothing added to commit but untracked files present (use "git add" to track)
```
#### Add e Commit

Se você fazer alguma alteração em um arquivo, o git irá comparar esse código com o HEAD e irá apontar dentro do `git status`. Para adicionar qualquer arquivo, use esse comando:
```cmd
C:\users\Ahosall\Workspace\hello-world> git add <nome_do_arquivo>
```

Agora se você está realmente confiante o suficiente para fazer essas mudanças no HEAD, então você pode usar o comando `commit`:
```
git commit -m "Adicionar qualquer mensagem sobre o commit aqui"
```

Depois de confirmar as alterações (e acreditar que elas estão prontas para serem enviadas para o repositório original), você pode usar o comando `push`.

Uma vez que o `git push origin master` é executado de dentro do diretório de trabalho, as mudanças presentes no *HEAD* são enviadas para o repositório remoto. No comando acima mencionado, o `master` pode ser alterado para o nome do branch ao qual você deseja que as alterações sejam comprometidas.

Se, no entanto, um repositório existente ainda não tiver sido clonado e você pretende estabelecer uma ligação entre o seu repositório e um servidor remoto, execute o seguinte comando:
```cmd
C:\users\Ahosall\Workspace\hello-world> git remote add origin <servidor>
```

> Nota: Substitua <servidor> pelo endereço do servidor remoto.
> Por exemplo: https://github.com/Ahosall/Hello-World.git

#### Branches
Outra característica brilhante (mas avançada) do GIT é sua capacidade de permitir que desenvolvedores e gerentes de projeto criem vários ramos (branches) independentes dentro de um único projeto.

O objetivo principal de um branch é desenvolver novas funcionalidades, mantendo-os isolados uns dos outros. O branch padrão em qualquer projeto é sempre o master branch. Tantos branches quanto necessários podem ser criados e eventualmente mesclados ao master branch.

Um novo branch pode ser criado usando o seguinte comando:
```cmd
C:\users\Ahosall\Workspace\hello-world> git checkout -b Ahosall
```
> `Ahosall` é o nome do branch.

Se você deseja retornar ao master branch, o seguinte comando pode ser usado:
```cmd
C:\users\Ahosall\Workspace\hello-world> git checkout master
```

Qualquer branch pode ser excluído usando o seguinte comando:
```cmd
C:\users\Ahosall\Workspace\hello-world> git checkout -d Ahosall
``` 

Para tornar o branch disponível para outros usuários, você terá que movê-lo para o repositório remoto. Para fazer isso, use o seguinte comando:
```cmd
C:\users\Ahosall\Workspace\hello-world> git push origin Ahosall
```

#### Atualizando e dando merge
Caso você queira atualizar seu diretório de trabalho local para o mais recente do repositório remoto, o simples comando git pull pode ser usado.

Para mesclar outro branch (dar um merge) no atualmente ativo, use: git merge feature_n.

Se você der um merge ou pull, o GIT sempre tenta lidar com os conflitos por conta própria, mas as vezes não consegue. Em caso de falha devido a conflitos, o usuário tem que resolver os conflitos manualmente. Depois de editar os arquivos (para erradicar conflitos), marque-os como merged usando:
```cmd
git add <nome.arquivo>
```
Se antes do merge você desejar visualizar as alterações, o seguinte comando pode ser executado:
```cmd
git diff <nome_branch_origem> <nome_branch_alvo>
```
> Fonte: [GIT Tutorial Para Iniciantes - O que é GIT?](https://www.hostinger.com.br/tutoriais/tutorial-do-git-basics-introducao)<br>