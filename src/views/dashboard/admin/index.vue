<template>
  <div class="dashboard-editor-container">
    <!-- <github-corner class="github-corner" /> -->
    <el-row :gutter="32">
      <el-col>
        <el-select v-model="value" filterable placeholder="请选择">
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
            </el-option>
        </el-select>
      </el-col>
    </el-row>
   
    <!-- <panel-group @handleSetLineChartData="handleSetLineChartData" /> -->
    <el-row :gutter="32">
      <!-- <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <raddar-chart />
        </div>
      </el-col> -->
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <pie-chart />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <bar-chart />
        </div>
      </el-col>
    </el-row>
    <el-row style="background:#fff;padding:16px 16px 0;margin-bottom:32px;">
      
        <div><line-chart :chart-data="lineChartData" />
        </div>
    </el-row>
  </div>
</template>

<script>


import LineChart from './components/LineChart'
// import RaddarChart from './components/RaddarChart'
import PieChart from './components/PieChart'
import BarChart from './components/BarChart'
// import TransactionTable from './components/TransactionTable'
// import TodoList from './components/TodoList'
// import BoxCard from './components/BoxCard'

// const lineChartData = {
//   newVisitis: {
//     expectedData: [100, 120, 161, 134, 105, 160, 165],
//     actualData: [120, 82, 91, 154, 162, 140, 145]
//   },
  // messages: {
  //   expectedData: [200, 192, 120, 144, 160, 130, 140],
  //   actualData: [180, 160, 151, 106, 145, 150, 130]
  // },
  // purchases: {
  //   expectedData: [80, 100, 121, 104, 105, 90, 100],
  //   actualData: [120, 90, 100, 138, 142, 130, 130]
  // },
  // shoppings: {
  //   expectedData: [130, 140, 141, 142, 145, 150, 160],
  //   actualData: [120, 82, 91, 154, 162, 140, 130]
  // }
// }

export default {
  name: 'DashboardAdmin',
  components: {
    // GithubCorner,
    // PanelGroup,
    LineChart,
    // RaddarChart,
    PieChart,
    BarChart,
    // TransactionTable,
    // TodoList,
    // BoxCard
  },
  data() {
    return {
       
        options: [{
          value: '选项1',
          label: '项目一'
        }, {
          value: '选项2',
          label: '项目二'
        }, {
          value: '选项3',
          label: '项目三'
        }, {
          value: '选项4',
          label: '项目四'
        }, {
          value: '选项5',
          label: '项目五'
        }],
       
      
      // lineChartData: lineChartData.newVisitis
    }
  },
  methods: {
    // handleSetLineChartData(type) {
    //   this.lineChartData = lineChartData[type]
    // }
  }
}
</script>

<style lang="scss" scoped>
.dashboard-editor-container {
  padding: 32px;
  background-color: rgb(240, 242, 245);
  position: relative;

  .github-corner {
    position: absolute;
    top: 0px;
    border: 0;
    right: 0;
  }

  .chart-wrapper {
    background: #fff;
    padding: 16px 16px 0;
    margin-bottom: 32px;
  }
}

@media (max-width:1024px) {
  .chart-wrapper {
    padding: 8px;
  }
}
</style>
