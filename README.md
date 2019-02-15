# iview-filter-table

> 一个基于iView Table 的带搜索过滤的Table组件, 支持 `Input`输入框 和  `Select`下拉框两种表格筛选方式.

![project.gif](https://github.com/azhengyongqin/iview-filter-table/blob/master/public/image/project.gif)

## 使用
**模板**：
```html
<filter-table @on-search="onSearch"
              :data="users"
              :columns="tableColumns">
</filter-table>
```
**列描述数据对象：**
```js
tableColumns: [
  {
    title: '用户名',
    key: 'username',
    filter: {
      type: 'Input' //输入框过滤
    }
  },
  {
    title: '状态',
    key: 'status',
    filter: {
      type: 'Select',//下拉框过滤
      option: userStatus //下拉框选项数据对象
    }
  }
]
```
**下拉框选项数据格式：**
```js
  const userStatus = {
    0: {
      value: 0,
      name: '全部'
    },
    1: {
      value: 1,
      name: '已锁定',
      color: 'red'
    },
    2: {
      value: 2,
      name: '正常',
      color: 'green'
    },
  };
```
**触发搜索事件：**

```js
onSearch(search) {
  //模拟数据库查询数据
  //这个search应该是传到后台,然后台来根据条件查询数据库
  alert('查询条件：'+JSON.stringify(search,null,4));
}
```

在该方法中进行条件过滤，更新组件 `data` 属性的值。

直接运行该项目可以看当前组件的Example效果。

![project.gif](https://github.com/azhengyongqin/iview-filter-table/blob/master/public/image/filterTable.gif)

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```

### Run your tests
```
yarn run test
```

### Lints and fixes files
```
yarn run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

**Github源码地址**
[![](https://img.shields.io/badge/Vue%E6%BA%90%E7%A0%81%E5%9C%B0%E5%9D%80-iview--filter--table-F37F40.svg)](https://github.com/azhengyongqin/iview-filter-table)
