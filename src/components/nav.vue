<template>
  <div>
    <el-menu default-active="1-1" theme="dark" :router="true">
      <el-submenu index="1">
        <template slot="title"><i class="el-icon-edit"></i>文章</template>
        <template v-if="level == 1">
          <el-menu-item index="1-1" :route="{path: '/art/addType'}">添加分类</el-menu-item>
          <el-menu-item index="1-2" :route="{path: '/art/addArt'}">添加公告</el-menu-item>
        </template>
        <el-menu-item index="1-3" :route="{path: '/art/verifyList'}">文章审核</el-menu-item>
        <el-menu-item index="1-4" :route="{path: '/art/verifyLog'}">审核记录</el-menu-item>
      </el-submenu>
      <el-submenu index="2">
        <template slot="title"><i class="el-icon-message"></i>导航一</template>
        <el-menu-item-group>
          <el-menu-item index="2-1">选项1</el-menu-item>
          <el-menu-item index="2-2">选项2</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
    </el-menu>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    data () {
      return {
        activeIndex: '/art/addType'
      };
    },
    methods: {
      handleOpen (key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose (key, keyPath) {
        console.log(key, keyPath);
      }
    },
    computed: {
      level () {
        return sessionStorage.getItem('level');
      }
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
</style>
