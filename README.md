# Guia básico sobre Git

Escritada adaptada do original https://github.com/SamuelHenn/guia-basico-git

Recomenda-se também o curso https://www.udemy.com/course/git-e-github-para-iniciantes/

## O que é o Git

O Git é um dos sistemas de **controle de versão** mais utilizados no mundo de desenvolvimento de software;

Isso significa que qualquer desenvolvedor numa equipe pode gerenciar o código-fonte e seu histórico de mudanças;

É software livre;


## Porque usar?

O Git pode ser usado em todo e qualquer projeto que tenha arquivos de diferentes tipos, podendo ser código, texto, imagens, vídeos, áudios, entre outros;

Desempenho / Segurança / Flexibilidade;

Compartilhar e organizar o código entre o time de desenvolvimento;

Backup e facilidade em reverter alterações;


## Interfaces usadas

São ferramentas para hospedar os respositórios;

Facilitam a visualização do repositório;

Agregam funcionalidades;

Podem ter custos;

- GitHub - Muito usado no "mundo open source"
- GitLab - Tem mais recursos de CI/CD e gerenciamento de tarefas
- BitBucket - Tem mais recursos de CI/CD e gerenciamento de tarefas


## Instalando

### Linux 

```bash
sudo apt-get install git
```

### Windows

- [Exe padrão para instalação](https://git-scm.com/download/win)


## Principais funções na prática


### Criar um repositório

* Crie uma conta no [GitHub](https://github.com/)

* Crie um projeto

* Observação: É possível usar o versionamento apenas localmente na máquina, mas o normal é que fique hospedado em algum serviço.


### Clonar o repositório


Cria uma cópia de trabalho local do projeto;

* Abra o terminal (caso esteja no Windows, pode ir até a pasta e clicar com o botão direito, aparecerá a opção de abrir o git bash na pasta)
* Navegue até a pasta desejada
```bash
git clone URL_DO_REPOSITÓRIO
```
* Informe usuário e senha

Configurar o usuário:
- Nome: ```git config --global user.name "NOME"```
- Email: ```git config --global user.email "EMAIL"```

### Mão na massa

- Crie um arquivo qualquer na pasta.

### Status

- Lista os arquivos que foram modificados: ```git status```

### Add

- Adiciona os arquivos modificados para serem comitados

	- Todos: ```git add .```


	- Por arquivo: ```git add CAMINHO_DO_ARQUIVO```


### Commit

Registra/salva as modificações que foram incluídas no 'add'

- Fazer o commit: ```git commit -m "Mensagem descrevendo o commit"```


### Push

Envia os commits locais para o servidor

- Fazer o push: ```git push```


### Pull

Busca as atualizações do repositório para o ambiente local

- Fazer o pull: ```git pull```

### Outros comandos úteis

Alguns comandos do Git que ajudam no dia a dia, especialmente para **desfazer**, **pausar** ou **investigar** alterações.

#### Visualizar diferenças
- `git diff` — mostra diferenças que ainda não foram adicionadas ao stage (`git add`).
- `git diff --staged` — mostra diferenças que já estão no stage.

#### Desfazer alterações
- `git restore <arquivo>` — descarta mudanças no *working tree* (cópia de trabalho).
- `git restore --staged <arquivo>` — remove o arquivo do stage, mas mantém as mudanças locais.
- `git reset --soft HEAD~1` — volta um commit mantendo tudo no stage.
- `git revert <hash>` — cria um commit que desfaz com segurança outro commit já publicado.

#### Stash – guardar alterações temporariamente
- `git stash` — salva alterações pendentes.
- `git stash list` — lista stashes salvos.
- `git stash show -p stash@{0}` — mostra o que há dentro do stash.
- `git stash pop` — aplica e remove o stash do topo.
- `git stash clear` — remove todos os stashes.

#### Cherry-pick & Rebase (avançado)
- `git cherry-pick <hash>` — aplica um commit específico na branch atual (também é útil para recuperar um arquivo de um commit ou branch específico).
- `git rebase -i HEAD~N` — reescreve interativamente os últimos *N* commits (editar, reordenar, squash).

#### Limpeza
- `git clean -fd` — remove arquivos/diretórios não rastreados (**cuidado!**).
- `git gc` — otimiza o repositório, removendo objetos órfãos.

> 💡 `git help <comando>` ou `git <comando> --help` traz detalhes completos e exemplos adicionais.


### Branchs

#### O que é uma branch

Branch significa “ramo”, ou seja, uma ramificação do seu código;

É usado para fazer modificações no código, sem afetar o código principal;

Representação gráfica:
![Branches](https://lh4.googleusercontent.com/hDZ7C2NQmOEeApDyPXFfjEfJyyIcmI8AfA8m-8loF8I2QKNrn4_Mw_IQKzoyj7O6SoKi2h6vTrKwZV5GL2uTJKSx_Kz8hSEpLAuhp7R_kpUYlW4H0oQbM34zo3fOZDtFU2PPtPr3)


#### Comandos

- Lista as branches existentes: ```git branch```

- Criar uma nova branch: ```git switch -b NOME_DA_BRANCH```

- Mudar de branch: ```git switch NOME_DA_BRANCH```


### Merge

Une a branch atual com outra branch

- Fazer o merge: ```git merge NOME_DA_BRANCH```


### Tag

Cria uma "versão do código" estática

Usado para versionar os projetos

- Listar as tags: ```git tag```

- Criar tag: ```git tag -a vNUMERO -m "DESCRICAO"```

- Envia a tag: ```git push origin vNUMERO```


## GitFlow

É uma ideia de como usar e organizar as branches;

É um fluxo de trabalho para o Git;

É um padrão que muitas empresas/projetos adotam, totalmente ou ao menos parciamente;

Imagem que representa o fluxo:

![GitFlow](https://lh3.googleusercontent.com/70jaEZnESXQ6SssU5uI4yO62JBz6xq2sNrrz8bW_ap2CuWUaQlbKs3j6NyRJnvcvYwAugkW8WzNJX21dZ2SMd9O_1TTpKZT-FsBkYSPy4rUSpJSo2C-WPTaLc2jQ8ancyj1TetXQ)


### Referência:
[Documentação Atlassian](https://www.atlassian.com/br/git/tutorials/what-is-version-control)
