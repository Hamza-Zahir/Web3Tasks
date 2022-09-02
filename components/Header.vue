<template>
  <div class="header py-1 m-0">
    <div class="d-flex container justify-content-around my-1 my-sm-2 text-center">
      <nuxt-link to="/" class="h4 py-2 px-3 mx-2">Web3 Projects</nuxt-link>
      <nuxt-link to="/Frontend_Projects" class="h4 py-2 px-3 mx-2"
        >Frontend Projects</nuxt-link
      >
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.header {
  background: #0c1a57;
}
a {
  color: #ffffff;
  text-decoration: none;
  border-radius: 15px;
  box-shadow: 0px 0px 5px #000000c9;
  font-size: 16px;

}
  @media (min-width:767px) {
a{
  font-size: 22px;
}
  }
a.nuxt-link-exact-active {
  background: #1a2c7e;
}
</style>
