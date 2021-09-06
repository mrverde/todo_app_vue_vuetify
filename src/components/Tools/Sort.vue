<template>
  <div>
    <v-btn v-if="!$store.state.sorting" @click="activateSort" icon>
      <v-icon>mdi-sort</v-icon>
    </v-btn>

    <v-btn v-else @click="activateSort" text small class="btn-finish-sort">
      Finish sort
    </v-btn>
  </div>
</template>

<script>
export default {
  methods: {
    activateSort() {
      if (!this.$store.state.search) {
        this.$store.commit("toggleSorting");
      } else {
        this.$store.commit(
          "showSnackbar",
          "How DARE you try to sort while searching!"
        );
      }
    },
  },
};
</script>

<style lang="sass">
.btn-finish-sort
  margin-top: 10px
  margin-right: 10px
  background: rgba(100, 100, 100, 0.3) !important
</style>
