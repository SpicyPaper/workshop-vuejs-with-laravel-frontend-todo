
<!--
TODO 5

Afficher les boutons Scoreboard, Counter et Logout uniquement quand l'utilisateur est loggedIn
Et afficher les boutons Register et Login unquement dans l'utilisateur n'est PAS loggedIn

(Indice 1 : v-if, computed)
(Indice 2 : this.$store permet d'accéder au store depuis n'importe qu'elle page)
-->

<!--
TODO 10.2

Importez le nouveau composant que vous venez de créer et remplacer le code du bouton concerné sur cette page par le composant
-->

<!--
TODO 11.2

Envoyez les bonnes données au nouveau permettant d'afficher le bouton Counter sur la navbar

(Indice 1 : Inspirez-vous de l'utilisation du composant CoffeeButton, dans le composant Counter)
-->

<!--
TODO 12

Utilisez ce nouveau composant pour modifier tous les boutons de la navbar : Scoreboard, Logout, Register et Login

(Indice 1 : Inspirez-vous de l'utilisation du composant CoffeeButton, dans le composant Counter)
-->

<template>
  <v-app-bar
    app
    dark
  >
    <h2>
      <router-link class="white--text" style="text-decoration: none" :to="{ name: 'home' }">
        <v-icon>mdi-coffee</v-icon>
        Coffee Counter
      </router-link>
    </h2>

    <v-spacer></v-spacer>

    <div v-if="loggedIn">
      <v-btn class="green darken-3 mr-3" :to="{ name: 'scoreboard' }">
        <span class="mr-2">Scoreboard</span>
        <v-icon>mdi-earth</v-icon>
      </v-btn>
      <NavButton></NavButton>
      <v-btn class="red darken-3 mr-3" :to="{ name: 'logout' }">
        <span class="mr-2">Logout</span>
        <v-icon>mdi-logout</v-icon>
      </v-btn>
    </div>
    <div v-else>
      <v-btn class="grey darken-3 mr-3" :to="{ name: 'register' }">
        <span class="mr-2">Register</span>
        <v-icon>mdi-account-plus</v-icon>
      </v-btn>
      <v-btn class="indigo darken-3 mr-3" :to="{ name: 'login' }">
        <span class="mr-2">Login</span>
        <v-icon>mdi-login</v-icon>
      </v-btn>
    </div>
  </v-app-bar>
</template>

<script>
import NavButton from './NavButton.vue'

export default {
  components: {
    NavButton,
  },
  computed: {
    loggedIn() {
      return this.$store.getters.loggedIn
    }
  }
}
</script>

<style>

</style>