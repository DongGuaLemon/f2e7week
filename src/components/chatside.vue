<template>
    <div class="side">
        <img :src="require(`../assets/small/${imgsrc}.png`)"/>
        <span>{{nickname}}</span>
        <span>今天天氣晴，肚子好餓。</span>
        <button>編輯</button>
        <div class="mode" @click="Nopen">
            <span>大廳<br />模式</span>
        </div>
        <div class="mode" @click="Nopen">
            <span>系統<br />配對</span>
        </div>
        
    </div>
</template>
<script>
export default {
    data() {
        return {
            nickname:'',
            imgsrc:''
        }
    },
    methods:{
        Nopen(){
            alert('暫無功能')
        }
    },
    mounted(){
        this.nickname=this.$route.params.id
        this.imgsrc=this.$route.params.img
    }
}
</script>
<style>
.side{
    width:25%;
    height:calc(100% - 56px);
    background-color:#766B6B; 
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
}
.side span{
    display: block;
    color:white;
}
.mode{
    width: 150px;
    height: 150px;
    border-radius: 50%;
    background-color: #524A4A;
    display: flex;
    justify-content: center;
    align-items: center;
}
.mode span{
    display: block;
}
.side button{
    background-color: #645B5B;
    border: unset;
    color:white;
    font-size: 12px;
}

</style>