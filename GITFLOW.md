# GitFlow

Hoje em dia utilizamos Git por padrão como ferramenta de desenvolvimento. Entretando não seguimos algumas coisas que
poderiam ser regras que ajudariam demais com organização de atualizações de projetos e no desenvolvimento em equipe.

O Gitflow ajudará principalmente nesses casos onde mais de uma pessoa está desenvolvendo features. Se isso ocorrer tudo numa mesma branch,
imagine a bagunça. O ideial é a utilização de uma branch para cada feature ou correção, para que haja uma independência e que, a branch ```master```/```main```, seja utilizada
somente quando tudo estiver funcionamento após a integração das branchs de features/correções. Essa junção deve ocorrer na ```develop``` e, somente após correções e finalizações, um merge para a branch principal (```master```/```main```).

**[Artigo sobre Gitflow e branches](https://medium.com/trainingcenter/utilizando-o-fluxo-git-flow-e63d5e0d5e04)**

## Padronização commits

É interessante seguirmos dois padrões em relação a commits:

### 1. Commits com uma só resposabilidade

Um commit deve conter somente uma resposabilidade, ou seja, deve ser feito somente alterações que se relacionam em um commit. Isso é excelente para entrarmos um problema
e saber em que momento ele apareceu na aplicação e também entermos a "história" da aplicação.

#### Exemplos

1. Em um módulo de autenticação, há duas coisas a serem implementadas: uma correção para transformar o email da pessoa em lowercase assim que chega na aplicação pois usuários estava tendo problemas utilizando alguma letra maiúscula no login, e autenticação de 2 fatores.
  Isso deve ser feito em dois commits diferentes. Um tem a resposabilidade correção, e outro de implementação de uma nova feature.
2. Existem correções a serem feitos no módulo de pedidos e no módulo administrativo: mesmo que sejam correções mínimas, faça-as em commits diferentes.

### 2. Padronização de mensagens de commit

Outra coisa para se entender o que foi feito num commit é a padronização das mensagens. Elas deve ter um padrão para que todos que leiam possam entender o que foi feito
naquele momento.

#### Regras

##### 1. Utilização do inglês por padrão

##### 2. Seguir a seguinte estrutura:

```[type](?[module]): [description]```

- ```type```: o tipo do commit:
  - ```fix```: para correções
  - ```refact```: para refatorações, ou seja, mudanças que não afetam o comportamento do código
  - ```feat```: para adições de novas features
- ```module``` (opcional): o módulo da aplicação que será afetado.
- ```description```: descrição breve do que feito feito no commit com a primeira letra minúscula

#### Exemplo:

Adicação de uma feature para exportação de relatórios em PDF em um módulo de pedidos:

```feat(orders): add pdf order export``` 