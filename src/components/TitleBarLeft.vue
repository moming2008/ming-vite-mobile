<template>

    <t-navbar :fixed="false" left-arrow>
      <template #left>
        <span class="custom-title">{{props.title}}</span>
      </template>
      <template #right>
        <t-icon name="home" size="24px" />
        <t-icon name="ellipsis" size="24px" />
      </template>
    </t-navbar>
  </template>
  
  <script lang="ts" setup>
  import { Icon as TIcon } from 'tdesign-icons-vue-next';
  const props = defineProps({
    title:String
  });
  </script>
  
  <style lang="less" scoped>
  .t-navbar {
    margin-bottom: 16px;
  }
  
  .custom-title {
    margin-left: 12px;
    font-size: 18px;
    font-weight: 600;
  }
  
  .t-icon-home {
    margin-right: 8px;
  }
  </style>