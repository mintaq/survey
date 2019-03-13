<template>
  <div id="app">
    <v-app id="inspire">
      <Header @toggleDrawer="toggleDrawer"/>

      <main>
        <v-content>
          <v-navigation-drawer v-model="drawer" fixed temporary app>
            <v-toolbar flat>
              <v-list>
                <v-list-tile>
                  <v-list-tile-title class="title">Application</v-list-tile-title>
                </v-list-tile>
              </v-list>
            </v-toolbar>
            <v-divider></v-divider>
            <v-list dense class="pt-0">
              <v-list-tile v-for="item in items" :key="item.title">
                <v-list-tile-action>
                  <v-icon>{{ item.icon }}</v-icon>
                </v-list-tile-action>

                <v-list-tile-content>
                  <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                </v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-navigation-drawer>
          <v-content>
            <v-container fluid>
              <router-view></router-view>
            </v-container>
          </v-content>
        </v-content>
      </main>
    </v-app>
  </div>
</template>

<script>
import Header from "./components/Header";

export default {
  data: () => ({
    drawer: null,
    left: false,
    items: [
      { title: "Home", icon: "home" },
      { title: "About", icon: "info" },
      { title: "Survey", icon: "remove_red_eye" }
    ]
  }),
  components: {
    Header
  },
  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    }
  }
};
</script>


<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
.danger-alert {
  color: red;
}
</style>