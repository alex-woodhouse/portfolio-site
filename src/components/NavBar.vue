<template>
  <div >
    <ul>
      <li class="active"><a href="">Home</a></li>
      <li><a href="#about">About Me</a></li>
      <li><a href="">My Works</a></li>
      <li><a href="">Contact Me</a></li>
      <li><a href="">Blog</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "NavBar"
}
</script>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 4px 16px;
  text-decoration: none;
}

.active {
  border-radius: 10px;
  border: 2px solid #FF1E56;
}
</style>
