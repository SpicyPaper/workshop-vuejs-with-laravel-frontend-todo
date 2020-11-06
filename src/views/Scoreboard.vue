<!--
TODO 13

Modifiez v-col pour afficher tous les utilisateurs.

(Indice 1 : v-for, key)
(Indice 2 : Attention appliquez les changements sur v-col et pas v-card)
-->

<template>
  <v-row v-if="authUser">
    <v-col v-for="user in users" :key="user.id"
      cols=12>
      <v-card
        class="mx-auto"
      >
        <v-card-title :class="user.id == authUser.id ? 'red--text' : 'blue--text'" style="justify-content: center;">
          {{ user.name }}
          -
          ({{ user.email }})
          <v-spacer></v-spacer>
          {{ user.coffee_counter }}
        </v-card-title>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  mounted() {
    this.fetchAllUsers();
  },
  methods: {
    fetchAllUsers() {
      this.$store.dispatch("fetchAllUsers")
    },
  },
  computed: {
    users() {
      return this.$store.getters.orderedUsers
    },
    authUser() {
      return this.$store.state.authUser
    }
  },
}
</script>

<style scoped>
  .coffee-counter {
    font-weight: bold;
    font-size: 1.3em;
  }
</style>