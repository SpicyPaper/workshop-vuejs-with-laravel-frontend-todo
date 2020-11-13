
<!--
TODO 10.1

Créer un nouveau composant ici, il doit contenir le code du bouton Counter de la navbar.

(Indice 1 : Inspirez-vous des autres composants)

> TIP 1 : Dans VSCode vous pouvez écrire <vue> et appuyer sur enter pour générer le template Vue de base.
-->

<!--
TODO 11.1

Utilisez les props pour abstraire un maximum d'éléments de ce composant.

(Indice 1 : Inspirez-vous du composant CoffeeButton)
(Indice 2 : Les éléments que vous devez abtraire sont : couleur, lien, texte, icon, sub icon)
-->

<template>
    <v-btn class="blue darken-3 mr-3" :to="{ name: 'counter' }">
        <span class="mr-2">Counter</span>
        <v-icon>mdi-coffee</v-icon>
        <v-icon>mdi-unfold-more-horizontal</v-icon>
    </v-btn>
</template>

<script>
export default {

}
</script>

<style>

</style>
