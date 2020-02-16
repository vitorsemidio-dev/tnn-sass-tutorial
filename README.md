# The Net Ninja - SASS Tutorial

## 1. Variáveis

Para criar uma variável um valor nela no sass basta iniciar com **$** seguido do nome. E para salvar um valor, deve-se adicionar após o dois pontos. Veja o exemplo abaixo:

```scss
  $deepBlue: #032f3e;
  $sectionHeading: 24px;

  #main-nav {
    background: $deepBlue;
  }

  section h1 {
    font-size: $sectionHeading;
    color: $deepBlue;
  }
```

Após ser compilado, o arquivo **.css** entenderá assim:

```css
  #main-nav {
    background: #032f3e;
  }

  section h1 {
    font-size: 24px;
    color: #032f3e;
  }
```

## 2. Mixin

É uma maneira de reaproveitar o código css em várias classes. Nós injetamos o código nos elementos que queremos, podendo adicionar novas estilos, se necessário. Estrutura inicial de um **mixin** segue o exemplo abaixo:

```scss
 @mixin nome-do-mixin {
   // estilos do mixin
   font-size: 10px;
   padding: 10px;
   margin: 10px;
 }
```

E para utilizá-lo em outros elementos devemos usar o **@include**. E também podemos adicinar estilos extras necessários para aquele elemento. Exemplo abaixo:

```scss
  .titulo-10 {
    @include nome-do-mixin;
    
    // novos estilos
    color: #00ffff;
    font-weight: bold;
    text-transform: uppercase;
  }

  .link-10 {
    @include nome-do-mixin;

    // novos estilos
    text-decoration: none;
    text-align: center;
  }
```

## 3. Import

Quando um arquivo **.scss** começa e ficar muito grande e responsável pela estilização de vários elementos, passa a ser interessante pensar na ideia de separar em outros arquivos alguns pedaços do código, modularizá-lo. Após ter separado o código em mais arquivo, nós podemos importar esses estilos em um único usando **@import**.

No exemplo sobre **variáveis** e **mixin** se todo o código estivesse em um só arquivo, poderíamos passar a deixar as variáveis em um chamado *variavel.scss* e os mixin em outro chamado *mixins.scss*. E no nosso arquivo principal, *styles.scss*, a gente importaria os estilos dos demais utilizando **@import** conforme exemplo abaixo:

```scss
  @import "variaveis.scss";
  @import "mixins.scss";

  #main-nav {
    background: $deepBlue;
  }

  section h1 {
    font-size: $sectionHeading;
    color: $deepBlue;
  }

  .titulo-10 {
    @include nome-do-mixin;
    
    // novos estilos
    color: #00ffff;
    font-weight: bold;
    text-transform: uppercase;
  }

  .link-10 {
    @include nome-do-mixin;

    // novos estilos
    text-decoration: none;
    text-align: center;
  }
```
## 4. Pseudo Classes e Operador &

Utilizar o **&** é extremamente útil para aninhamento e até evitar certas repetições. Normalmente estilizamos uma classe/id/tag. E dps queremos um estilo diferente para quando ela sofre algum evento de *active*/*focus*/*hover* etc...

Ao invés de fazer assim: 

```scss
  .class {
    // estilo
  }

  .class:hover {
    // estilo para quando sofrer evento de "hover"
  }
  
  .class:focus {
    // estilo para quando sofrer evento de "focus"
  }

  .class .sub-class  {
    // estilo para sub-class
  }
```

Podemos utilizar o operador **&** dentro da classe **.class**, e o código fica assim:

```scss
  .class {
    // estilo da classe .class
  
    &:hover {
      // estilo para quando sofrer evento de "hover"
    }
    
    &:focus {
      // estilo para quando sofrer evento de "focus"
    }
  
    &.sub-class {
      // estilo para sub-class
    }

  }
```
