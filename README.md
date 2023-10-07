# Jtamodal

# Description

Ce composant permet d'afficher (de superposer) un container au centre de l'écran.

<p><img src="src/images/1.png" /></p>

1. Le clic sur l'icône "Fermer" déclenche le Onclick correspondant (Voir settings)
2. Le clic sur Le bouton "Annuler" déclenche le Onclick correspondant (Voir settings)
3. Le clic sur le bouton "Ok" déclenche le Onclick correspondant (Voir settings)
4. Vous pouvez mettre ce que vous voulez dans la zone de travail (scrollable verticalement)

- Un clic à **l'extérieur** de la fenêtre modale déclenche le Onclick de l'icone "Fermer" 
- On peut faire disparaitre le footer (voir settings). La zone de travail occupera alors la totalité du container

# Utilisation

Vous ferez apparaitre et disparaitre ce container avec une condition associée à ce composant <br>
(Par exemple, la condition d'apparition du container sera la présence d'un state. Pour faire disparaitre le container, il suffira de configurer les différents évènements Onclick pour supprimer ce state)

**NB** : Ne pas oublier de déclarer un background color pour pouvoir masquer le contenu de l'écran qui se trouvera sous le container

> **Astuce** : Pour modifier un style dans la zone de travail, dérivez le style **jta_modal_inner**
>
> Exemple : Pour afficher les label en blanc, créer un Embed dans lequel vous mettrez : 
> ```
> <style>
> .jta_modal_inner label{
>     color:white!important;
> }
> </style>
> ```

## Instructions

To build your new  plugin run the following in your Budibase CLI:
```
budi plugins --build
```

You can also re-build everytime you make a change to your plugin with the command:
```
budi plugins --watch
```

Find out more about [Budibase](https://github.com/Budibase/budibase).
