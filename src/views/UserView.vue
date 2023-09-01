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
            <span class="target_number">{{ target_item.target }}</span>
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
    <t-cell-group bordered>
    <t-cell title="单行标题" arrow hover />
    <t-cell title="单行标题" arrow hover required />
    <t-cell title="单行标题" arrow hover>
      <template #note>
        <t-badge :count="16" />
      </template>
    </t-cell>
    <t-cell title="单行标题" hover>
      <template #note>
        <t-switch :default-value="true" />
      </template>
    </t-cell>
    <t-cell title="单行标题" note="辅助信息" arrow hover />
    <t-cell title="单行标题" :left-icon="lockIcon" arrow hover />
  </t-cell-group>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import TitleBarLeft from '../components/TitleBarLeft.vue'

import { h } from 'vue';
import { LockOnIcon } from 'tdesign-icons-vue-next';
import { Switch as TSwitch, Badge as TBadge } from 'tdesign-mobile-vue';

const lockIcon = () => h(LockOnIcon);
const imgUrl = 'https://tdesign.gtimg.com/miniprogram/images/example1.png'

const target_list = ref([
  {index:0,label:'关注',target:813},
  {index:1,label:'被关注',target:987},
  {index:2,label:'收藏',target:14},
  {index:3,label:'浏览',target:1122}
])

</script>

<style>
.avatar-example {
  margin-left: 24px;
  margin-top: 24px;
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
    margin: 8px auto;
    &>div{
      margin: 8px 18px;
      font-family:Alibaba-PuHuiTi-Regular;
      color: #0b5681;
      .target_number{
        font-size: 20px;
        color: #ffffff;
        font-family:Montserrat-Medium;
      }
    }

  }
  .user_info {
    margin-top: 20px;
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
