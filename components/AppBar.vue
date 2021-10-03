<template>
  <el-menu
    router
    :default-active="activeIndex"
    mode="horizontal"
  >
    <el-menu-item index="/">Home</el-menu-item>
    <el-menu-item index="/portfolio">Portfolio</el-menu-item>
    <el-menu-item index="/photos">Photos</el-menu-item>
    <el-menu-item index="/contact">Contact</el-menu-item>
    <el-menu-item index="/about">About</el-menu-item>
  </el-menu>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: this.$router.history.current.fullPath
      };
    },
  }
</script>
