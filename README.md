Le web sémantique ne date pas d'hier mais il me semble encore assez peu utilisé. Nous allons créer dans un premier temps une structure de page HTML5 assez simple puis nous allons ajouter des micro-données.

Structure d'une page HTML5
----------------------------------

Les principales balises introduites en HTML5 sont les suivantes :

### La balise "section"
Cette balise permet de définir des zones dans une application, un article ou un document. Cela sera sans doute la balise la plus utilisée dans les documents HTML5.

### La balise "nav"
Cette balise est une "section" particulière qui permet d'identifier les liens de navigation. Bien entendu, tous les liens n'ont pas à être encadrés par cette balise. Toutefois, il faut comprendre que cette balise ne sert pas uniquement pour la navigation principale. Elle peut être utilisée pour l'ensemble des blocs de liens, comme par exemple dans le footer.

### La balise "aside"
L'élément aside représente une "section" également particulière de votre page. Elle permet de définir une zone secondaire adjacent au contenu principale. L'utilisation la plus fréquente est en tant que sidebar.

### La balise "hgroup"
C'est sans doute l'élément le moins utilisé aujourd'hui alors que son utilisation est très pratique. Cela permet de regroupé des tags de titres et sous-titres (h1 -> h6). Par example, un titre avec une baseline.

### La balise "header"
Cette balise représente une section d'introduction. Elle peut être utilisée dans des sections comme "article" par exemple, ou encore dans une section "nav" pour insérer un logo.

### La balise "footer"
Cet élément va être utilisé pour mettre en valeur un contenu de conclusion. Nous pourrons donc trouver un élément footer pour l'application complète mais aussi à l'intérieur d'un article.

### La balise "main"
Cet élément est utilisé pour encadrer le contenu principal comme par exemple le contenu d'un article de blog.

> Il faut garder à l'esprit que tout est lié à la hiérarchisation de vos éléments et plus particulièrement à celle de votre contenu.

Par exemple, ces deux approches ne signifient pas du tout la même chose pour l'organisation de votre contenu :

```html
<header>
Mon blog vous parle des outils web !
</header>
<article>
Ceci est un article qui parle de Web sémantique.
</article>
```

```html
<article>
	<header>
	Cet article explique les balises introduites par HTML5
	</header>
Ceci est un article qui parle de Web sémantique.
</article>
```

Construisons une page type pour un blog ! Ci-contre un schémas récapitulatif :
![schemas](www.ouanounou.fr/public/schemas.png)

```html
<!DOCTYPE html>
<head>
    <title>Une page type de blog en HTML5</title>
</head>
<body>
    <header>

    </header>
    <nav>

    </nav>
    <aside>

    </aside>
    <section>
        <header>

        </header>
        <article>
            <header>

            </header>
            <main>

            </main>
            <footer>
                
            </footer>
        </article>
        <article>
            <header>

            </header>
            <main>

            </main>
            <footer>

            </footer>
        </article>
        <aside>
            
        </aside>
        <aside>
            
        </aside>
        <footer>
            
        </footer>
    </section>
    <section>
        
    </section>
    <footer>
        
    </footer>
</body>
</html>
```

J'utilise pour ma part énormément Bootstrap. Nous allons donc construire cette page avec l'aide de cette librairie CSS en essayant de reproduire notre schémas.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Une page type de blog en HTML5</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootswatch/3.3.5/united/bootstrap.min.css">
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="">
        <header class="header col-xs-12 col-sm-12 col-md-12 col-lg-12">
            Site header
        </header>
        <nav class="nav col-xs-12 col-sm-12 col-md-12 col-lg-12">
            Navigation
        </nav>
        <aside class="aside col-xs-2 col-sm-2 col-md-2 col-lg-2">
            Aside
        </aside>
        <section class="section-content col-xs-10 col-sm-10 col-md-10 col-lg-10">
            <header class="header col-xs-12 col-sm-12 col-md-12 col-lg-12">
                Section header
            </header>
            <div class="articles col-xs-8 col-sm-8 col-md-8 col-lg-8">
                <article class="article col-xs-12 col-sm-12 col-md-12 col-lg-12">
                    <header class="header col-xs-12 col-sm-12 col-md-12 col-lg-12">
                        Article header
                    </header>
                    <main class="main col-xs-12 col-sm-12 col-md-12 col-lg-12">
                        Article content
                    </main>
                    <footer class="footer col-xs-12 col-sm-12 col-md-12 col-lg-12">
                        Article footer
                    </footer>
                </article>
                <article class="article col-xs-12 col-sm-12 col-md-12 col-lg-12">
                    <header class="header col-xs-12 col-sm-12 col-md-12 col-lg-12">
                        Article header
                    </header>
                    <main class="main col-xs-12 col-sm-12 col-md-12 col-lg-12">
                        Article content
                    </main>
                    <footer  class="footer col-xs-12 col-sm-12 col-md-12 col-lg-12">
                        Article footer
                    </footer>
                </article>
            </div>
            <div class="asides col-xs-4 col-sm-4 col-md-4 col-lg-4">
                <aside class="aside-min col-xs-12 col-sm-12 col-md-12 col-lg-12">
                    Section aside
                </aside>
                <aside class="aside-min col-xs-12 col-sm-12 col-md-12 col-lg-12">
                    Section aside
                </aside>
            </div>
            <footer class="footer col-xs-12 col-sm-12 col-md-12 col-lg-12">
                Section footer
            </footer>
    </section>
    </div>
    <footer class="footer col-xs-12 col-sm-12 col-md-12 col-lg-12">
        Site footer
    </footer>
</body>
</html>
```

Le style css associé (styles.css) : 
```css
.header{
    height:30px;
    background-color: #444444;
}

.nav{
    height:50px;
    background-color: #737373;
}

.aside{
    height:500px;
    background-color: #545454;
}

.aside-min{
    height:150px;
    background-color: #545454;
    margin-top: 5px;
}

.section-content{
    height:500px;
    background-color: #696e14;
    padding:10px;
}

.articles{
    padding-left:0;
    padding-right:0;
}

.article{
    height:205px;
    background-color: #0a396e;
    margin-top:5px;
    padding:5px;
}

.main{
    height:130px;
    background-color: #127fe7;
}

.footer{
    height:30px;
    background-color: #d6d6d6;
    margin-top: 5px;
}
```
Nous avons maintenant une structure bien hiérarchisée bien que nous n'ayons pas utilisé toutes les balises à notre disposition, la balise hgroup par exemple.

Ci-contre un tableau de l'ensemble des "balise" ajoutée par HTML5 :

| Balise  |  Description |
|---|---|
|article  |Définit un article  |
|aside   |Définit un contenu à côté du contenu principal   |
|details   |Définit une zone d'information que l'utilisateur peut afficher ou cacher   |
|figcaption   |Définit "caption" pour un élément "figure"   |
|figure   |Spécifie un élément de contenu "entier" comme une images, un diagramme ou encore une illustration   |
|footer   |Définit une zone de conclusion ou de fin pour un document ou un article et plus généralement une section   |
|header   |Définit une zone d'introduction ou de début pour un document ou un article et plus généralement une section   |
|main   |Définit le contenu principale d'un document comme par exemple le coeur d'un article   |
|mark   |Définit un text mis en valeur   |
|nav   |Définit une zone de navigation principale, secondaire ou simplement une liste de lien   |
|section   |Définit une zone d'un document (article/footer/header/main/aside sont des sections particulières)   |
|summary   |Définit une entête pour élément "details"   |
|time   |Définit une date et/ou une heure   |
|---|---|

Vous trouverez toute la documentation sur [w3schools](http://www.w3schools.com/tags/default.asp).


