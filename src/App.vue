<template>
  <v-app>
    <v-navigation-drawer
        v-model="drawer"
        absolute
        temporary
        class="hidden-md-and-up"
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Navigation
          </v-list-item-title>
        </v-list-item-content>
        <v-list-item-action>
          <v-icon @click="drawer = false;">
            mdi-close
          </v-icon>
        </v-list-item-action>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
          nav
          dense
      >
        <v-list-item-group
            v-model="group"
            active-class="text--accent-4"
        >
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>About Me</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-briefcase</v-icon>
            </v-list-item-icon>
            <v-list-item-title>My Works</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-card-account-mail</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Contact Me</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-post</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Blog</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <Home class="home" @toggleDrawer="toggleDrawer"></Home>
<!--    <About id="about"></About>-->
    <MyWorks id="myworks"></MyWorks>
  </v-app>
</template>
<style>
.home {
  width: 100%;
  height: 100vh;
}

html {
  scroll-behavior: smooth;
}

::-webkit-scrollbar {
  width: 20px;
}

::-webkit-scrollbar-track {
  background-color: transparent;
}
::-webkit-scrollbar-thumb {
  background-color: #6a6969;
  border-radius: 20px;
  border: 6px solid transparent;
  background-clip: content-box;
}

::-webkit-scrollbar-thumb:hover {
  background-color: #a8bbbf;
}
</style>

<script>
import Home from "@/components/Sections/Home/Home";
// import About from "@/components/Sections/About/About";
import MyWorks from "@/components/Sections/MyWorks/MyWorks";

export default {
  name: 'App',

  components: {
    MyWorks,
    // About,
    Home,
  },

  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    }
  },

  data: () => ({
    drawer: false,
  }),
};
</script>
