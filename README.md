# element-datatable

> 一款基于element-ui的表格插件，支持所有element-ui的属性和方法，可以接受本地数据和ajax参数异步请求服务器数据
> A form plug-in based on element-ui that supports the properties and methods of all element-ui and can accept local data or ajax parameter asynchronous request server data

## 相关依赖 Dependencies
* [axios](https://github.com/axios/axios), [element-ui](http://element.eleme.io), [qs](https://github.com/ljharb/qs)
* IE >= 9

## 基本用法 Build Setup
* 安装 install
``` bash
npm i element-datatable -S
```
* 在项目中引入element-ui依赖,参见http://element.eleme.io. 引入element相关的css文件.

* 使用本地数据 use local data
```html
<template>
  <div id="app">
    <element-datatable :column-attributes="columnAttributes" :data="tableData" />
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
      tableData: [
        {
          date: '2018-09-30',
          content: '123',
          isDelay: false,
          delayReason: '',
          checked: true
        }
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
  }
}
</script>
```
* 使用ajax获取数据 get data by ajax
```html
<template>
  <div id="app">
    <element-datatable :column-attributes="columnAttributes" :ajax="ajax" />
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
      tableData: [
        {
          date: '2018-09-30',
          content: '123',
          isDelay: false,
          delayReason: '',
          checked: true
        }
      ],
      columnAttributes: [
        { label: "序号", type: 'index', width: '50', align: 'center' },
        { type: 'selection', align: 'center', width: 55 },
        { label: '日期', prop: 'date', width: '120', align: 'center', sortable: true },
        { label: '工作内容', prop: 'content', headerAlign: 'center', },
        { label: '工期是否延误', prop: 'isDelay', headerAlign: 'center', width: 130 },
        { label: '延误原因', prop: 'delayReason', headerAlign: 'center' }
      ],
      ajax: {
        url: '',
        method: '',
        headers: {},
        params: {},
        data: {}
      }
    }
  }
}
</script>
```
有关el-table和el-table-column使用方法，请参考[element-ui](http://element.eleme.io/#/zh-CN/component/table)相关说明

## 其它功能 Other property & event
* 支持所有的el-table、el-table-column属性、事件和方法.

* checked-prop
  仅在tyep="selection"时有效，该属性接收一个字符串指定某一属性或方法，通过验证数据的指定属性值确认是否选中该条数据；方法接收两个参数(row, index), 通过返回true或false指定该数据是否选中

* selectAbleProp
  仅在tyep="selection"时有效，该属性接收一个字符串指定某一属性，通过验证数据的该属性值判断是否可选，作用与el-table-column的selectable属性相同。
