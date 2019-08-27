<template>
    <div class="chatview">
        <side />
        <chatlist />
    </div>
</template>
<script>
import side from '../components/chatside'
import Navbar from "@/components/Navbar.vue";
import chatlist from '../components/chatlist.vue'
export default {
    components:{
        side,
        Navbar,
        chatlist
    }
}
</script>
<style>
.chatview{
    width: 100%;
    height: 100%;
    display: flex;
}

</style>