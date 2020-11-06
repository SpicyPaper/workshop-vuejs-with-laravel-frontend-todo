
<!--
TODO 4

Ajouter le composant NavBar à l'endroit indiqué sur cette page.

(Indice 1 : N'oubliez pas d'importer le composant)
(Indice 2 : Utilisez components)
-->

<template>
  <v-app>
    <!-- Ajoutez le composant NavBar ici -->
    <v-main>
      <v-container>
        <router-view></router-view>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
// import TestComponent from './'

export default {
  name: 'App',

  created() {
    if (this.loggedIn) {
      this.$store.dispatch("fetchAuthUser")
    }
  },

  components: {
  },

  computed: {
    loggedIn() {
      return this.$store.getters.loggedIn
    }
  },

  data: () => ({
    //
  }),
};
</script>
