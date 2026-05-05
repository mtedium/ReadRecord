<template>
  <div class="common-layout">
    <el-container>
      <el-header>
        <el-menu
          :default-active="activeIndex"
          class="el-menu-demo"
          mode="horizontal"
          :ellipsis="false"
          @select="handleSelect"
        >
          <el-menu-item index="0">
            <img
              style="width: 100px"
              src="https://element-plus.org/images/element-plus-logo.svg"
              alt="Element logo"
            />
          </el-menu-item>
          <el-menu-item index="1"
            ><NuxtLink to="/">主页</NuxtLink></el-menu-item
          >
          <!-- <el-sub-menu index="2">
            <template #title>Workspace</template>
            <el-menu-item index="2-1">item one</el-menu-item>
            <el-sub-menu index="2-2">
              <template #title>item two</template>
              <el-menu-item index="2-2-1">item one</el-menu-item>
            </el-sub-menu>
          </el-sub-menu>
          <el-menu-item index="3" disabled>Info</el-menu-item>
          <el-menu-item index="4">Orders</el-menu-item> -->
        </el-menu>
      </el-header>

      <el-main>
        <NuxtPage />
      </el-main>

      <el-footer>Footer</el-footer>
    </el-container>
  </div>
</template>

<script lang="ts" setup>
// import { ref } from "vue";

const activeIndex = ref("1");
const handleSelect = (key: string, keyPath: string[]) => {
  console.log(key, keyPath);
};
</script>

<style scoped>
/* .el-menu--horizontal > .el-menu-item:nth-child(1) {
  margin-right: auto;
} */
</style>
