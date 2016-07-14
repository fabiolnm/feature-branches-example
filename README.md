## Tutorial de Feature Branches

A facilidade de utilização de feature branches no Git é provavelmente o grande trunfo que faz desta ferramenta superior aos seus concorrentes (CVS, Subversion, Mercurial para dar alguns exemplos). 

Um segundo grande trunfo é o Github, que fornece ferramentas fantásticas para:
1. Merge via Pull Requests é muito intuitivo!
2. Diálogo de merge dá indicações se:
  2.1. Não houver conflitos
  2.2. Os testes estiverem passando no CI
  2.3. O código novo possui falhas de segurança ou violações de qualidade segundo a análise estática do Code Climate.
3. Incentiva a prática de code reviews, pois 
  3.1. a ferramenta de PRs é integrada com a diff da branch
  3.2. possui suporte built-in a comentários diretamente em cada linha de código.

A intuição deste tutorial é ser um guia rápido para ajudar na familiarização do que seria um uso recomendado de feature branches.

<img width="300" alt="exemplo" src="https://github.com/fabiolnm/feature-branches-example/blob/tutorial/images/grafico_de_rede.png?raw=true">

Na ilustração acima, temos:

1. Linha preta é a branch de referência, nomeada de master.
2. AC criou uma branch (verde) e fez um commit, partindo do commit inicial.
3. Em paralelo, Fábio criou outra branch (azul).
4. Fábio e AC seguiram commitando paralelamente, até que AC integrou o seu trabalho de volta à master.
5. Alfa cria uma nova branch (roxa), partindo deste ponto (após AC integrar).
6. AC inicia uma nova feature, em uma nova branch (amarela)
7. Fábio termina seu trabalho na branch azul e precisa integrar na master.
  7.1. Primeiro, Fábio traz as atualizações da master para a sua branch
  7.2. Em seguida, Fábio integra a sua branch para a master.

### Comandos

#### Criar nova branch

Normalmente uma branch parte da master, mas nada impede que haja uma sub-branch de uma branch.

```
git checkout -b nova_branch
```

### Integrar a branch de volta para a master

Existem dois caminhos
 * 1. Visual, com cliques de botão, usando os Pull Requests do Github
  * 1.1. Vantagens: simples, intuitivo, facilita verificações de CI e Code Climate integradas ao Github, facilita code reviews (ferramenta de diff e de comentários integradas)
  * 1.2. Desvantagem: ruim pra quem prefere trabalhar apenas na linha de comando, ou não vê necessidade de fazer code review.
 * 2. Linha de comando: a tela de Pull Requests do Github fornece os comandos para fazer merge sem precisar criar um PR.
