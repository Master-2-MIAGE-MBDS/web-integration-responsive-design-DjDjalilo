# TP1 HTML/CSS

## Login

La page de login statique utilise une structure de layout comme suit :

<img src="https://github.com/Master-2-MIAGE-MBDS/web-integration-responsive-design-DjDjalilo/blob/main/Login.png" width="250" height="400" />

![#f03c15](https://via.placeholder.com/15/f03c15/f03c15.png) represante la structure principale en Grid Layout avec un template de type HEADER-BODY-FOOTER.
```css
.container{
    height: 100vh;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 10% 1fr 8%;
    grid-template-areas: 
    'header'
    'main'
    'footer';
}
```

![#fff200](https://via.placeholder.com/15/fff200/fff200.png) ![#ffc90e](https://via.placeholder.com/15/ffc90e/ffc90e.png) ![#efe4b0](https://via.placeholder.com/15/efe4b0/efe4b0.png) ces couleurs jaunatre represante le reste de la structure en Flexible Layout principalement dans le BODY.


- Le HEADER/FOOTER :
  - Contiennent seulement du text pour le nom de l'application et une mention des droits d'auteur.
- Le BODY :
  - On va prendre l'exemple de la couleur ![#fff200](https://via.placeholder.com/15/fff200/fff200.png) le BODY est alors divise en deux partie a l'aide d'un Flex Layout en colonne :
  ```css
  .main{
    grid-area: main;
    display: flex;
    flex-direction: column;
    justify-content: center;
   }
  ```
  Ainsi que la partie Welcome et des identifiants sont les Items de cette derniere, le reste suit le meme principe.

## AdList (version mobile) 










