<script setup>
 defineProps({
  count:{
    type:Number,
  },
})




</script>


<template>
  <div id="app" class="pbar">
    <div class="shell">
      <div class="bar" :style="{ width:count  + '%' }">
      </div>
    </div>

  </div>
  </template>
  
  <style>
  .pbar {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .shell {
  background: rgba(242, 243, 243, 0.6);
    height: 11px;
    width: 260px;
    border: none;
    border-radius: 13px;
  }

  .bar {
    background: rgba(59, 222, 124, 1);
    height: 11px;
    width: 15px;
    border-radius: 13px;
  }

  button {
    margin: 10px;
    border: 1px solid #aaa;
    background: none;
    border-radius: 50%;
    padding: 5px 8px;
    outline: none;
    cursor: pointer;
  }
  </style>