## Proto collision

Afin de pouvoir traiter les collisions entre deux objets il me faut quatres donnéees en particulier, les deux blocs étant **positionnés de manière absolue**, ces données pourront me permettre de vérifier si les positions concordent. Ces données sont :

* les positions **top** pour:
    * le tonneau (le tonneau est une class avec des propriétés propres)
    * la plateforme (chaque plateforme est une entrée de tableau)
* les positions **left** pour:
    * le tonneau
    * la plateforme

Dans le script de base du projet, chaque tonneau est réinitialisé à un intervale prédéfini symbolisant un mouvement (dans ce cas une chute), je devrais donc vérifier à chaque *frame* si les positions entrent en conflit ou non, en **pseudo-code**, voici donc mon raisonnement, cette boucle s'effectuant donc à chaque intervale :

```
    POUR CHAQUE plateforme
        SI position-y du tonneau >= position-y plateforme
        ET position-x du tonneau >= position-x plateforme - largeur du tonneau
        ET position-x du tonneau <= position-x du tonneau + largeur de la plateforme
            CLEAR interval
```