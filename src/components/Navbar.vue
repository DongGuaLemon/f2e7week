<template>
  <div>
    <b-navbar toggleable="lg" class="navbar">
      <b-navbar-brand href="#"><router-link to="/"><span>Chatroom</span></router-link></b-navbar-brand>
    </b-navbar>
  </div>
</template>
<script>
export default {};
</script>
<style>
.navbar {
  background: #524a4a 0% 0% no-repeat padding-box;
}
.navbar span {
  font: Regular 24px/36px Noto Sans TC Medium;
  letter-spacing: 0.48px;
  color: #a59696;
}
</style>