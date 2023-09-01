<template>
  <div class="user">
    <TitleBarLeft title="用户中心" />
    <div class="user_panel">
      <div class="user_box">
        <t-avatar
          class="avatar-example"
          image="https://tdesign.gtimg.com/mobile/demos/avatar_1.png"
          shape="circle"
        ></t-avatar>
        <div class="user_info">
          <span class="user_name">Darren Adams</span>
          <span class="user_detail">Actor</span>
        </div>
      </div>
      <div class="user_target">
        <div v-for ="target_item in target_list" :key="target_item.index">
            <span>{{ target_item.target }}</span>
            <br/>
            <span>{{ target_item.label }}</span>
          </div>
      </div>
    </div>
    <t-grid class="grid-demo">
      <t-grid-item text="标题文字" :image="imgUrl" />
      <t-grid-item text="标题文字" :image="imgUrl" />
      <t-grid-item text="标题文字" :image="imgUrl" />
      <t-grid-item text="最多五个字" :image="imgUrl" />
    </t-grid>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import TitleBarLeft from '../components/TitleBarLeft.vue'
const imgUrl = 'https://tdesign.gtimg.com/miniprogram/images/example1.png'

const target_list = ref([
  {index:0,label:'target',target:12},
  {index:1,label:'target',target:12},
  {index:2,label:'target',target:12},
  {index:3,label:'target',target:12}
])

</script>

<style>
.avatar-example {
  margin-left: 16px;
  margin-top: 16px;
}
.grid-demo {
  margin-bottom: 16px;
}
.user_panel {
  flex-direction: column;
  background: linear-gradient(#4224eb, #0e92eb);
  height: 160px;
  border-radius: 10px;
  display: flex;
  .user_box {
    display: flex;
  }
  .user_target{
    display: flex;
    text-align: center;
    &>div{
      margin: 14px;
      font-family:Montserrat-Bold;
      color: #dbeaf3;
    }

  }
  .user_info {
    margin-top: 12px;
    padding-left: 16px;
    display: flex;
    flex-direction: column;

    .user_name {
      font-size: 18px;
      color: aliceblue;
      font-family: Montserrat-Bold;
    }
    .user_detail {
      font-size: 16px;
      color: rgb(172, 198, 221);
      font-family: Montserrat-Regular;
    }
  }
}
</style>
