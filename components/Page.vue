<template>
  <el-container class="container">
    <el-header>
      <AppBar />
    </el-header>
    <el-main>
      <slot></slot>
    </el-main>
    <el-footer> Copyright © Jesper Hansson Falkenby 2021 </el-footer>
  </el-container>
</template>

<style>
.container {
  height: calc(100vh - 16px); /* body margins = 16px */
  width: calc(100vw - 16px); /* body margins = 16px */
}
</style>
