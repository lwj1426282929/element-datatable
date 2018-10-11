<template>
  <div id="app">
    <el-input v-model="searchObj.val" />
    <el-button @click='search'>查询</el-button>
    <element-datatable ref="table" :server-params="searchObj" :ajax="ajax" :column-attributes="columnAttributes" />
  </div>
</template>

<script>
import ElementDatatable from './components'
export default {
  name: "App",
  components: {
    ElementDatatable
  },
  data() {
    return {
      searchObj: {
        val: '',
        startTime: '2018-10-11 00:00:00',
        endTime: '2018-10-11 23:59:59'
      },
      ajax: {
        url: 'ind/target/query', // 也可以直接写http地址
        method: 'post', // 默认get请求
        data: { // data
          target_name: 'get_xd_handon_count_index'
        }
      },
      tableData: [
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true },
        { date: '2018-09-30', content: '123', isDelay: false, delayReason: '', checked: true }
      ],
      columnAttributes: [
        { label: "序号", type: 'index', width: '50', align: 'center' },
        { type: 'selection', align: 'center', width: 55 },
        { label: '日期', prop: 'date', width: '120', align: 'center', sortable: true },
        { label: '工作内容', prop: 'content', headerAlign: 'center', },
        { label: '工期是否延误', prop: 'isDelay', headerAlign: 'center', width: 130 },
        { label: '延误原因', prop: 'delayReason', headerAlign: 'center' }
      ]
    }
  },
  methods: {
    search() {
      this.$refs.table.reloadData()
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
