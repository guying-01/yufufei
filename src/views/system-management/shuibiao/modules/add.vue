<!--
 * @Author       : gy
 * @Date         : 2021-02-16 18:26:27
 * @LastEditors: gy
 * @LastEditTime: 2021-02-23 11:11:51
 * @FilePath     : /yufufei/src/views/system-management/dianbiao/modules/add.vue
 * @Description  : 页面描述
-->
<template>
  <el-form ref="form" :model="form" style="padding:0 20px;" label-width="120px">
    <el-form-item label="水表类型">
      <el-select v-model="form.field8" placeholder="请选择">
        <el-option :value="1" label="阀控" />
        <el-option :value="2" label="Modbus" />
      </el-select>
    </el-form-item>
    <el-form-item label="仪表编号">
      <el-input v-model="form.field2" />
    </el-form-item>
    <el-form-item label="生产编号">
      <el-input v-model="form.field4" />
    </el-form-item>
    <el-form-item label="网关编号">
      <el-select v-model="form.field3" placeholder="请选择">
        <el-option label="" :value="1">
          <div class="flex">
            <div>主键</div>
            <div>网关编号</div>
          </div>
        </el-option>
        <el-option label="019006" value="019006">
          <div class="flex">
            <div>190977979899</div>
            <div>019006</div>
          </div>
        </el-option>
        <el-option label="019008" value="019008">
          <div class="flex">
            <div>190977979899</div>
            <div>019008</div>
          </div>
        </el-option>
      </el-select>
    </el-form-item>
    <el-form-item label="型号">
      <el-input v-model="form.field6" />
    </el-form-item>
    <el-form-item label="商铺号">
      <el-input v-model="form.field5" />
    </el-form-item>
    <el-form-item label="备注">
      <el-input v-model="form.field7" />
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
        field8: 1

      }
    }
  },
  mounted() {},
  methods: {}
}
</script>
<style lang="scss" scoped>
.flex {
  justify-content: space-around;
  div {
    width: 150px;
  }
}
</style>
