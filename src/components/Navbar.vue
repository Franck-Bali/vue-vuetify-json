<template>
    <div class="app">
        <v-app-bar color="red accent-3" dark dense>
            <!--v-app-bar-nav-icon></v-app-bar-nav-icon-->
            <v-toolbar-title>Zawarudo</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn class="mr-5" icon small v-for="(i , k) in links" :key="k" router :to="i.route">
                <v-icon small>{{i.icon}}</v-icon>
            </v-btn>
            <v-menu left bottom>
                <template>
                    <v-btn icon>
                        <v-icon>mdi-dots-vertical</v-icon>
                    </v-btn>
                </template>
            </v-menu>
        </v-app-bar>
    </div>
</template>

<script>
  export default {
    name : "Navbar",
    data(){
      return{
        links: [
          {icon: 'mdi-home', route: '/'},
          {icon: 'mdi-heart-pulse', route: '/News'},
        ],
      }
    }
  }
</script>

<style>

</style>
