<!--
 * @Author       : gy
 * @Date         : 2021-02-16 18:26:27
 * @LastEditors  : gy
 * @LastEditTime : 2021-02-17 19:38:00
 * @FilePath     : /yufufei/src/views/system-management/role/modules/add.vue
 * @Description  : 页面描述
-->
<template>
  <el-form ref="form" :model="form" style="padding:0 20px;" label-width="120px">
    <el-form-item label="角色名称">
      <el-input v-model="form.field1" />
    </el-form-item>
    <el-form-item label="角色描述">
      <el-input v-model="form.field2" type="textarea" />
    </el-form-item>
  </el-form>
</template>

<script>
export default {
  components: {},
  props: {},
  data() {
    return {
      form: {

      }
    }
  },
  mounted() {},
  methods: {}
}
</script>
<style lang="scss" scoped>
</style>
