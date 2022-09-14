# TP1 HTML/CSS

Note : 

![#f03c15](https://via.placeholder.com/15/f03c15/f03c15.png) represante les zones/parties qui utilisant un Grid Layout.

![#fff200](https://via.placeholder.com/15/fff200/fff200.png) ![#ffc90e](https://via.placeholder.com/15/ffc90e/ffc90e.png) ![#efe4b0](https://via.placeholder.com/15/efe4b0/efe4b0.png) represante les zones/parties utilisant un Flexible Layout.

Ceci est valable pour les deux page LOGIN et ADLIST.


## 1- Login

La page de login statique utilise une structure de layout comme suit :

<img src="https://github.com/Master-2-MIAGE-MBDS/web-integration-responsive-design-DjDjalilo/blob/main/ReadmeSupportPics/Login.png" width="250" height="400" />

![#f03c15](https://via.placeholder.com/15/f03c15/f03c15.png) represante la structure principale en Grid Layout avec un template de type HEADER-BODY-FOOTER en colonne.

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

## 2- AdList (version mobile) 

La page de listing d’annonces statique utilise une structure de layout comme suit :

<img src="https://github.com/Master-2-MIAGE-MBDS/web-integration-responsive-design-DjDjalilo/blob/main/ReadmeSupportPics/AdList_Mob.png" width="250" height="400" />

![#f03c15](https://via.placeholder.com/15/f03c15/f03c15.png) represante la structure principale en Grid Layout avec un template de type HEADER-BODY-FOOTER (comme avec la page LOGIN).
```css
.container{
    height: 100vh;
    display: grid;
    grid-template-columns: auto;
    grid-template-rows: 1.5fr 10fr 0.75fr;
    grid-template-areas:
    "header"
    "main"
    "footer"
}
```
- Le HEADER/FOOTER :
  - Contiennent seulement du text pour le nom de l'application et une mention des droits d'auteur (qui peuvent potentiellemnt modifier leur comportement en fonction du type du pehipherique desktop ou mobile).
- Le BODY :
  - On va prendre l'exemple de la couleur ![#fff200](https://via.placeholder.com/15/fff200/fff200.png) le BODY contient des Ads qui sont des items de la FlexBox BODY, ainsi, via le CSS si dessous, les Ads vont etre disposee une en dessous de l'autre en colonne :
  ```css
  .main{
    grid-area: main;
    display: flex;
    flex-direction: column;
    justify-content:flex-start;
    margin: 15px;
  }
  ```
  - Ces Ads utilisent eux meme un FlexLayout pour le disposition de leurs contenues comme le montre la couleur ![#ffc90e](https://via.placeholder.com/15/ffc90e/ffc90e.png) une partie pour l'icone de l'annonce, ainsi qu'une autre pour sa description et son prix.

## 3- AdList (version Desktop)
  
Modification du CSS pour faire en sorte que notre WebView de [AdList](https://github.com/Master-2-MIAGE-MBDS/web-integration-responsive-design-DjDjalilo/blob/main/README.md#adlist-version-mobile), ce qui donne comme resultat :

<img src="https://github.com/Master-2-MIAGE-MBDS/web-integration-responsive-design-DjDjalilo/blob/main/ReadmeSupportPics/transi%20mob-web.gif" width="700" height="450" />

Et cela grace aux Media queries quand ajoute dans notre CSS qui ressemble a ceci  :
```css
@media screen and (min-width: 650px) {
    ...
    .main{
        grid-area: main;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        flex-wrap: wrap;
        margin: 15px;
    }
    ...
```
- 'screen' designe le type de média, dans notre cas, on cherche a vise les appareil ayant un ecran large (Desktop).
- 'and' est l'operateur logique.
- 'min-width: 650px' ceci veut dire que des lors le navigateur web (desktop/mobile) detecte un ecran avec une largeur de minimum 650px, alors il applique le CSS qui est compris dans le bloc entre { } et tout cela, de facon dynamique (comme montre dans le gif ci dessus)






