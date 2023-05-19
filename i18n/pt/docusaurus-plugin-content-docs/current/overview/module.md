---
sidebar_position: 4
---

# Módulos

Antes de explicar o que é um módulo único, vamos falar primeiro sobre o que é um módulo de contêiner.

Um módulo de contêiner é uma coleção de serviços, no nosso caso mais especificamente `Controllers` e suas dependências que podem ser registrados e resolvidos pelo contêiner InversifyJS.

Um módulo de contêiner é uma classe que exporta um objeto Module do inversify, que é essencialmente um objeto de configuração que define as ligações entre serviços (no Expresso TS, serviços são Controllers) e suas dependências. O objeto Module possui um método de ligação que permite definir ligações entre serviços e suas dependências.

Com o ExpressoTS, você não precisa se preocupar em fazer ligações manualmente, criamos uma função auxiliar chamada `CreateModule` que recebe um array de controladores e retorna um módulo com todos os controladores registrados e suas dependências injetadas.

:::caution ALERTA DE SPOILER
Estamos criando um mecanismo para que você possa determinar os tipos de vinculação de suas classes, para ter mais controle sobre as ligações, decidindo quando usar o escopo `Singleton`, `Transient` ou `Request`.
:::

## Módulo Container

Um módulo de contêiner é tipicamente usado para agrupar controladores relacionados e suas dependências, tornando mais fácil registrá-los e gerenciá-los no contêiner. Por exemplo, você pode criar um módulo de contêiner que define os bindings para um conjunto de controladores de acesso a dados, ou um conjunto de serviços de lógica de negócios.

Uma vez que um módulo de contêiner tenha sido definido, ele pode ser carregado no `AppContainer` usando o método `appContainer.create()`, que recebe a classe do módulo de contêiner como argumento. Isso registrará todos os serviços e dependências definidos no módulo no contêiner, tornando-os disponíveis para injeção em outras partes da sua aplicação.

Módulos de contêiner podem ser uma ferramenta poderosa para gerenciar grandes aplicações com gráficos de dependência complexos, pois permitem que você organize seu código em partes menores e mais gerenciáveis e tornem mais fácil o entendimento das relações entre diferentes partes da aplicação.

Um módulo de contêiner, ou simplesmente um módulo Expresso TS, é definido no exemplo abaixo:

```typescript
const AppModule = CreateModule([
    AppController,
]);

export { AppModule };
```

---

## Apoie o projeto

Expresso TS é um projeto de código aberto licenciado sob o MIT. É um projeto independente com desenvolvimento contínuo possibilitado graças ao seu suporte. Se você deseja ajudar, por favor considere:

- Se tornar um **[Sponsor no GitHub](https://github.com/sponsors/expressots)**
- Siga a **[organização](https://github.com/expressots)** no GitHub e de um Star ⭐ no projeto
- Subscreva no nosso canal na Twitch: **[Richard Zampieri](https://www.twitch.tv/richardzampieri)**
- Entre no nosso **[Discord](https://discord.com/invite/PyPJfGK)**
- Contribua submetendo **[issues e pull requests](https://github.com/expressots/expressots/issues/new/choose)**
- Compartilhe o projeto com seus amigos e colegas