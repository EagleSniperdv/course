<script setup></script>

<template>
  <div class="layout">
    Layout: default
    <slot></slot>
  </div>
</template>

<style scoped>
.layout {
  padding: 12px;
  /* margin: 15px; */
  background-color: #1c83c7;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
