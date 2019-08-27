<template>
  <div class="chartlist">
    <ul>
      <li v-for="(item,index) in list" :key="index" :class="item.team">
        <div class="imgname">
          <img :src="require(`../assets/small/${item.src}.png`)" width="35px" height="35px" class="chatimg" />
          <span>{{item.name}}</span>
        </div>
        <div :class="chatlog+item.team">
          <span>{{item.label}}</span>
        </div>
      </li>
    </ul>
    <div class="submit">
      <div class="subleft">
        <i class="material-icons">sentiment_satisfied_alt</i>
        <i class="material-icons">insert_photo</i>
        <i class="material-icons">attach_file</i>
      </div>
      <input v-model="text" @keyup.enter="submit" placeholder="輸入文字" />
      <div class="subright" @click="submit">
        <i class="material-icons">send</i>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      show: true,
      list: [
        {
          name: "小貓咪",
          team: "guest",
          src: 'cat-4',
          label:
            "美中貿易戰再升級，中國大陸23日宣布對750億美元 進口美國商品分批加徵關稅後，美國總統川普隨即 「命令」美企撤出中國大陸，並將大陸國家主席習 近平稱為「敵人」，更表示要將總值約5,500億美元 大陸輸美商品加徵關稅的稅率，分批提升5個百分點"
        },
        {
          name: "煞氣a仔仔",
          team: "guest",
          src: 'cat-2',
          label: "安安，萬華彭于晏～哪裡人？萬華彭于晏是真的嗎？"
        },
        {
          name: "我就喵喵喵",
          team: "guest",
          src: 'cat-3',
          label: "安安，萬華彭于晏～很高興認識你～"
        },
        {
          name: "小宅宅",
          team: "guest",
          src: 'cat-1',
          label: "安安，萬華彭于晏～真的～～好深奧～～～～～～～～"
        }
      ],
      chatlog: "chatlog",
      text: "",
      nickname:'',
      imgrc:''
    };
  },
  methods: {
    submit() {
      if (this.text != "") {
        this.list.push({
          name: this.nickname,
          src: this.imgsrc,
          team: "host",
          label: this.text
        });
        this.text = "";
      }
    }
  },
  mounted(){
      this.nickname=this.$route.params.id
      this.imgsrc=this.$route.params.img
  }
};
</script>
<style scoped>
.material-icons {
  color: white;
}
.chartlist {
  width: 100%;
  height: 100%;
  overflow: scroll;
  position: relative;
}
i{
    cursor: pointer;
}
.submit {
  position: fixed;
  bottom: 10px;
  left: 30%;
  width: 60%;
  height: 40px;
  background-color: #968686;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.submit input {
  background-color: #968686;
  border-right-style: solid;
  border-left-style: solid;
  border-top-style: unset;
  border-bottom-style: unset;
  color: white;
  padding-left: 10px;
  width: 80%;
}
.subleft {
  width: 10%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.subright {
  display: flex;
  align-items: center;
}
.chatimg {
  vertical-align: middle;
  display: inline-block;
}
.chartlist li {
  display: flex;
  align-items: center;
  margin-top: 5%;
  /* flex-direction: row-reverse */
}
.host {
  flex-direction: row-reverse;
}
.chartlist ul {
  margin-top: 15px;
  margin-bottom: 150px;
}
.imgname {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 80px;
}
.imgname span {
  color: white;
  font-size: 12px;
}
.chatlogguest {
  margin-left: 20px;
  background-color: #524a4a;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  padding: 15px;
  max-width: 550px;
  position: relative;
  word-break: break-all;
  /* --left: -10;  */
}

.chatlogguest::before {
  position: absolute;
  top: 8px;
  left: -10px;
  content: " ";
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 7.5px 13px 7.5px 0;
  border-color: transparent #524a4a transparent transparent;
}
.chatloghost {
  margin-left: 20px;
  background-color: #524a4a;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  padding: 15px;
  max-width: 550px;
  position: relative;
  word-break: break-all;
}
.chatloghost::before {
  position: absolute;
  top: 8px;
  right: -10px;
  content: " ";
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 7.5px 0 7.5px 13px;
  border-color: transparent transparent transparent #524a4a;
}
/* border-width: 7.5px 0 7.5px 13.0px; */
</style>