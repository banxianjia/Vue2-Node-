<template>
  <view class="emoji" :style="{height:height+'px'}">
    <view class="emoji-line" v-for="(line, i) in emoji" :key="i">
     <view class="emoji-line-item" v-for="(item, index) in line" :key="index" @tap="clickEmoji(item)">
       {{item}}
     </view> 
    </view>
  </view>
</template>

<script>
  export default {
    props:{
      height:{
        type:Number,
        default:230
      }
    },
    data() {
      return {
        emoji:[
          ['😀','😁','😂','🤣','😃','😄','😅','😆',],
          ['😉','😊','😋','😎','😍','😘','😗','😙',],
          ['😚','🙂','🙂','🤗','🤔','😐','😑','😶',],
          ['🙄','😏','😣','😥','😮','🤐','😯','😪',],
          ['😫','😴','😌','😛','😜','😝','🤤','😒',],
          ['😖','😞','😟','😤','😢','😭','😦','😧',],
          ['😨','😩','😬','😰','😱','😳','😵','😡',],
          ['😠','😷','🤒','🤕','🤢','🤧','😇','🤠',],
          ['😓','😔','😕','🙃','🤑','😲','🙁','👥',],
          ['🤡','🤥','🤓','😈','👿','👹','👺','💀',],
          ['👻','👽','🤖','💩','😺','😸','😹','😻',],
          ['😼','😽','🙀','😿','😾','👫','👬','👭',],
          ['⛑','🏻','🏻','🏽','🏾','🏿','🗣','👤',],
          ['👂','👂🏻','👂🏼','👂🏽','👂🏾','👂🏿','👃','👃🏻',],
          ['👃🏼','👃🏽','👃🏾','👃🏿','👣','👀','👁','👅',],
          ['👄','💋','👓','🕶','👔','👕','👖','👗',],
          ['👘','👙','👚','👛','👜','👝','🎒','👞',],
          ['👟','👠','👡','👢','👑','👒','🎩','🎓',],
          ['💄','💍','🌂','💼',],
        ]
      }
    },
    methods: {
      clickEmoji(item){
        this.$emit('curemoji',item)
      }
    }
  }
</script>

<style lang="scss">
.emoji{
    width: 100%;
    height: 460rpx;
    padding: 10rpx;
    box-sizing: border-box;
    overflow: hidden;
    overflow-y: auto;
    .emoji-line{
      display: flex;
      flex-direction: row;
      justify-content: flex-start;
      .emoji-line-item{
        text-align: center;
        width: 80rpx;
        height: 80rpx;
        font-size: 48rpx;
        margin: 10rpx;
        line-height: 68rpx;
      }
    }
}
</style>
