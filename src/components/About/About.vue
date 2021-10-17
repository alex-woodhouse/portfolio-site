<template>
  <div class="about">
    <v-row
        no-gutters
        style="flex-wrap: nowrap;"
    >
      <v-col>
        <h1 style="margin-left: 10%" class="text-lg-h2 font-weight-bold mt-8">About Me</h1>
      </v-col>
      <v-col>
        <div class="about-me-graphic"></div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
name: "About"
}
</script>

<style scoped>
h1 {
  position:relative;
  z-index:1;
  color: #202040;
}
h1:after {
  content:"";
  position:absolute;
  width:170px;
  height:30px;
  background-color:#FF1E56;
  left:0px;
  bottom:0px;
  z-index:-1;
}

.about {
  background-color: white;
}
.about-me-graphic {
  background-image: url(../../assets/about_me.svg);
  width: 100%;
  height: 100vh;
}
</style>
