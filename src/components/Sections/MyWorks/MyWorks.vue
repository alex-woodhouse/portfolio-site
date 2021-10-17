<template>
  <div class="my-works">
    <h1 style="" class="text-lg-h2 font-weight-bold mt-8">My Works</h1>
  </div>
</template>

<script>
export default {
name: "MyWorks"
}
</script>

<style scoped>
  h1 {
    position:relative;
    z-index:1;
    color: #202040;
    margin-left: 10%;
  }
  h1:after {
    content:"";
    position:absolute;
    width:10vw;
    height:30px;
    background-color:#FF1E56;
    left:0px;
    bottom:0px;
    z-index:-1;
  }
  .my-works {
    width: 100%;
    height: 100vh;
    background-color: white;
  }


</style>
