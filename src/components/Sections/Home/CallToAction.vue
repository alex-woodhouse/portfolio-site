<template>
  <div>
    <h1 class="text-lg-h1 text-md-h2 text-sm-h2 text-  font-weight-bold mb-lg-6 mr-5">Alex Woodhouse</h1>
    <h3 class="text-lg-h3 font-weight-thin">Full Stack Web Developer</h3>
    <div class="btn-divider"/>
    <div class="d-flex flex-wrap">
      <v-btn class="btn-glow mr-4 mb-3" height="50" width="170" color="#FF1E56" depressed href="#myworks">
        <span>See My Works</span>
      </v-btn>
      <v-btn height="50" width="170" color="#FF1E56" outlined href="mailto:contact@alexwoodhouse.co.uk">
        <span class="white--text">Contact Me</span>
      </v-btn>
    </div>
  </div>
</template>

<script>
export default {
  name: "CallToAction"
}
</script>

<style scoped>
h1 {
  color: #FF1E56;
}

.btn-divider {
  width: 70px;
  height: 5px;
  background-color: white;
  margin: 30px 0;
}

.btn-glow {
  box-shadow: 5px 5px 15px rgba(255, 30, 86, 0.25);
}
</style>
