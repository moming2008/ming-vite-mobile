<template>
    <t-tab-bar v-model="value" shape="round" theme="tag" :split="false">
      <t-tab-bar-item v-for="item in list" :key="item.value" :value="item.value" >
            <template #icon>
                <RouterLink :to="item.link">
                <t-icon :name="item.icon" :class="[isActiveIndex==item.index?'tab_item_active' :'tab_item']" style="font-size: 24px;" @click="tabBarClicked(item.index)"/>
               </RouterLink> 
            </template>
      </t-tab-bar-item>
    </t-tab-bar>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  import { Icon as TIcon } from 'tdesign-icons-vue-next';
  import { RouterLink } from 'vue-router'
  
  const value = ref('label_1')
  var isActiveIndex = 1
  const list = ref([
    { value: 'label_1', label: '首页', icon: 'home',link:'/' ,index:1},
    { value: 'label_2', label: '应用', icon: 'app' ,link:'/about',index:2},
    { value: 'label_3', label: '聊天', icon: 'chat' ,link:'/',index:3},
    { value: 'label_4', label: '我的', icon: 'user' ,link:'/user',index:4},
  ]);

  function tabBarClicked(index:number){
    console.log("index"+index)
    isActiveIndex = index
    console.log("isActiveIndex"+index)
  }
  </script>

  <style>

  .tab_item_active{
    color: blue;
  }
  .tab_item{
    color: black;
  }

.wrapper {
  --td-tab-bar-border-color: #e7e7e7;
  --td-tab-bar-bg-color: #eee;
  --td-tab-bar-hover-color: #ddd;
  --td-tab-bar-item-color: #bbb;
  --td-tab-bar-item-active-color: #333;
}
</style>