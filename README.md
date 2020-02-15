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
