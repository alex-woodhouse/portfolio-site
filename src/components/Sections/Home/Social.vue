<template>
  <div class="d-flex pb-8">
    <a href="https://www.linkedin.com/in/alexander-woodhouse/" target="_blank">
      <div class="linkedin" />
    </a>
    <a href="https://github.com/alex-woodhouse/" target="_blank">
      <div class="github ml-3" />
    </a>
  </div>
</template>

<script>
export default {
name: "Social"
}
</script>

<style scoped>
.linkedin {
  background-image: url(../../../assets/social/linkedin.svg);
  width: 50px;
  height: 50px;
}
.github {
  background-image: url(../../../assets/social/github.svg);
  width: 50px;
  height: 50px;
}
</style>
