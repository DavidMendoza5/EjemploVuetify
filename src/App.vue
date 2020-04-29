<template>
  <v-app>
    <v-app-bar dense dark app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Inicio</v-toolbar-title>
      <!--    <v-btn
          color=#E8A766
          dark
          @click.stop="drawer = !drawer"
        >
          Log In
          </v-btn>
          !-->
      <v-btn rounded >About us</v-btn>
       <v-spacer></v-spacer>
        <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://github.githubassets.com/images/modules/logos_page/Octocat.png"></v-img>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title>Huastec</v-list-item-title>
        </v-list-item-content>
        </v-list-item>
        <v-divider></v-divider>
         <v-list dense>

        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        drawer: null,
        items: [
          { title: 'Log in', icon: 'dashboard' },
          { title: 'Sign up', icon: 'question_answer' },
        ],
      }
    },
  }
</script>