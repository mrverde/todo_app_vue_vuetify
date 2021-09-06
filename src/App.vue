<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" :mobile-breakpoint="768" app>
      <v-img
        class="pa-4 pt-7"
        height="170"
        src="mountains.jpg"
        gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
      >
        <v-avatar size="70" class="mb-2">
          <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
        </v-avatar>
        <div class="white--text text-subtitle-1 font-weight-bold">John Doe</div>
        <div class="white--text text-subtitle-2">john_doe_334</div>
      </v-img>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="primary"
      dark
      src="mountains.jpg"
      prominent
      :height="$route.path === '/' ? 230 : 170"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.9), rgba(128,208,199,.9)"
        ></v-img>
      </template>

      <v-container class="header-container mt-3 pa-0">
        <v-row>
          <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
          <v-spacer></v-spacer>
          <search></search>
          <sort></sort>
        </v-row>
        <v-row>
          <v-toolbar-title class="text-h4 ml-4">
            {{ appTitle }}
          </v-toolbar-title>
        </v-row>
        <v-row>
          <live-date-time />
        </v-row>
        <v-row v-if="$route.path === '/'">
          <field-add-task />
        </v-row>
      </v-container>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
      <snackbar />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: null,
    items: [
      { title: "Todo", icon: "mdi-format-list-checks", to: "/" },
      { title: "About", icon: "mdi-information", to: "/about" },
    ],
  }),
  mounted() {
    this.$store.dispatch("getTasks");
  },
  computed: {
    appTitle() {
      return process.env.VUE_APP_TITLE;
    },
  },
  components: {
    "field-add-task": require("@/components/Todo/FieldAddTask.vue").default,
    snackbar: require("@/components/Shared/Snackbar.vue").default,
    search: require("@/components/Tools/Search.vue").default,
    sort: require("@/components/Tools/Sort.vue").default,
    "live-date-time": require("@/components/Tools/LiveDateTime.vue").default,
  },
};
</script>

<style lang="sass">
.header-container
  max-width: none !important
</style>
