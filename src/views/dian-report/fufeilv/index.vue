<template>
  <div>
    <el-row :gutter="20">
      <el-col :span="4">
        <div style="padding:20px">
          <el-checkbox v-model="checkAll" @change="handleCheckboxChange">
            全选
          </el-checkbox>
        </div>

        <el-tree
          ref="tree"
          :data="treeList"
          :default-expand-all="true"
          :show-checkbox="true"
          node-key="id"
        />
      </el-col>
      <el-col :span="20">
        <div class="list-page">
          <FilterPanel>
            <div class="filters">
              <el-form
                ref="form"
                :model="form"
                label-width="80px"
                label-position="left"
              >
                <el-row :gutter="20">
                  <el-col :span="8">
                    <el-form-item label="创建时间:">
                      <el-date-picker
                        v-model="form.prop1"
                        type="daterange"
                        range-separator="至"
                        start-placeholder="开始日期"
                        end-placeholder="结束日期"
                      />
                    </el-form-item>
                  </el-col>
                  <el-col :span="8">
                    <el-form-item label="商铺号:">
                      <el-input v-model="form.prop2" placeholder="商铺号" />
                    </el-form-item>
                  </el-col>
                  <el-col :span="8">
                    <el-button type="primary" @click="getList">查询</el-button>
                    <el-button type="success" @click="handleExport">导出</el-button>
                  </el-col>
                </el-row>
              </el-form>
            </div>
          </FilterPanel>

          <div class="list">
            <comm-table
              :data="tableData"
              :static-table="true"
              @selection-change="selectionChange"
            >
              <el-table-column label="开始时间" prop="field1" />
              <el-table-column label="结束时间" prop="field2" />
              <el-table-column label="表号" prop="field3" />
              <el-table-column label="商铺号" prop="field4" />
              <el-table-column label="上次抄表" prop="field5" />
              <el-table-column label="本次抄表" prop="field6" />
              <el-table-column label="用电量" prop="field7" />
              <el-table-column label="尖电量" prop="field8" />
              <el-table-column label="峰电量" prop="field9" />
              <el-table-column label="平电量" prop="field10" />
              <el-table-column label="谷电量" prop="field11" />
              <el-table-column label="上次余额" prop="field12" />
              <el-table-column label="本次余额" prop="field13" />
              <el-table-column label="购电金额" prop="field14" />
              <el-table-column label="使用金额" prop="field15" />
              <el-table-column label="互感器倍率" prop="field16" />
              <el-table-column label="备注" prop="field17" />

            </comm-table>
          </div>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import TableMixin from '@/mixins/TableCommMixin'
export default {
  name: 'DianReportFufeilv',
  mixins: [TableMixin],
  props: {},
  data() {
    return {
      checkAll: false,
      form: {},
      treeList: [
        {
          label: '101:隆泰物业',
          id: 1,
          children: [
            {
              label: '09115:测试',
              id: 2
            }
          ]
        },
        {
          label: '103:4G表测试',
          id: 3,
          children: [
            {
              label: '019079:4G表',
              id: 4
            }
          ]
        }
      ],
      tableData: [
        { field1: '2021-02-25', field2: '2021-02-25', field3: '019148051C', field4: '宿舍总表', field5: '0.00', field6: '0.00', field7: '0.00', field8: '-1.00', field9: '-1.00', field10: '-1.00', field11: '-1.00', field12: '0.00', field13: '0.00', field14: '0.00', field15: '0.00', field16: '30', field17: '' },
        { field1: '2021-02-25', field2: '2021-02-25', field3: '019148051B', field4: '洗衣房1', field5: '151.48', field6: '151.48', field7: '0.00', field8: '-1.00', field9: '-1.00', field10: '-152.48', field11: '-1.00', field12: '-184.1600	', field13: '0184.16', field14: '0.00', field15: '0.00', field16: '1', field17: '总表' }
      ]
    }
  },
  created() {
    this.form.prop1 = [new Date(), new Date()]
  },
  mounted() {},
  methods: {
    handleCheckboxChange(val) {
      this.$refs.tree.setCheckedNodes(val ? this.treeList : [])
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
