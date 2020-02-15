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
