<template>
  <el-menu
    router
    :default-active="activeIndex"
    mode="horizontal"
    @select="handleSelect"
  >
    <el-menu-item index="/">Home</el-menu-item>
    <el-menu-item index="/photos">Photos</el-menu-item>
    <el-menu-item index="/about">About</el-menu-item>
    <el-menu-item index="/contact">Contact</el-menu-item>
  </el-menu>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: this.$router.history.current.fullPath
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>

<style>
</style>
