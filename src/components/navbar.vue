<template>
  <nav>
    <v-toolbar app flat>
      <v-toolbar-side-icon class="grey--text" @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title class="grey--text">
        <span class="font-weight-light">ADMIN</span>
        <span class="underline">DASHBOARD</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn flat left class="grey--text">
        <span>Login</span>
        <v-icon right>lock_open</v-icon>
      </v-btn>

    </v-toolbar>
    <v-navigation-drawer class="indigo pa-4" v-model="drawer" app>
      <v-list>
        <v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
          <v-list-tile-action>
            <v-icon class="white--text">
              {{ link.icon }}
            </v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="white--text">
              {{ link.text }}
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      links: [
        {icon: 'dashboard', text: 'Dashboard', route: '/'},
        {icon: 'info', text: 'About', route: '/about'}
      ]
    }
  }
}
</script>
