<template>
  <div class="home">
    <v-row
        no-gutters
        style="flex-wrap: nowrap;"
    >
      <v-col class="home-left hidden-sm-and-down" md="4" lg="6">
        <img class="home-left-img" src="https://unsplash.com/photos/N5bT5RctFZ8/download?force=true&w=1000" alt="">
      </v-col>
      <v-col class="home-right-bg" sm="12" md=8 lg="6">
        <div class="home-right">
          <div>
            <v-icon @click="$emit('toggleDrawer')" class="mt-8 hidden-md-and-up ">mdi-menu</v-icon>
            <NavBar class="mt-10 hidden-sm-and-down"></NavBar>
          </div>
          <CallToAction></CallToAction>
          <Social></Social>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import CallToAction from "@/components/Home/CallToAction";
import Social from "@/components/Home/Social";
import NavBar from "@/components/NavBar";

export default {
  name: "Home",
  components: {
    NavBar,
    Social,
    CallToAction
  },
}
</script>

<style scoped>
.home {
  display: flex;
  min-height: 100vh;
  max-height: 100vh;
}

.home-left-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.home-right-bg {
  background-color: #202040;
  background-image: url(../assets/home_shapes_bg.svg);
}
.home-right {
  height: 100%;
  padding-left: 8%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

</style>
