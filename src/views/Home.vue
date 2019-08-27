<template>
  <div class="home">
    <div class="homeinfo">
      <Login />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Login from "@/components/Login.vue";
export default {
  name: "home",
  components: {
    Navbar,
    Login
  }
};
</script>
<style>
.home {
  width: 100%;
  height: calc(100% - 10px);
  display: flex;
  flex-direction: column;
}
.homeinfo {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>