
[![](https://img.shields.io/badge/%E5%8E%9F%E6%96%87%E5%9C%B0%E5%9D%80-CSDN-FF4567.svg)](https://blog.csdn.net/qq_23179075/article/details/79939244)
[![](https://img.shields.io/badge/Vue%E6%BA%90%E7%A0%81%E5%9C%B0%E5%9D%80-iview--filter--table-F37F40.svg)](https://github.com/azhengyongqin/iview-filter-table)
[![](https://img.shields.io/badge/CSDN-%40印象丶亮仔-%23F45555.svg)](https://blog.csdn.net/qq_23179075)
[![](https://img.shields.io/badge/Github-%40azhengyongqin-brightgreen.svg)](https://github.com/azhengyongqin)
[![](https://img.shields.io/badge/Vue.js-2.0-41B883.svg)](https://cn.vuejs.org)
[![](https://img.shields.io/badge/iView-2.0-blue.svg)](https://www.iviewui.com)
# iview-filter-table

> 一个基于iView Table 的带搜索过滤的Table组件, 支持 `Input`输入框 和  `Select`下拉框两种表格筛选方式.

![filterTable.gif](https://upload-images.jianshu.io/upload_images/2909848-6ebb4e553dfb18bc.gif?imageMogr2/auto-orient/strip)

## 使用
**模板**
```vue
    <filter-table @load="loadData" //过滤触发事件
                  :data="users"
                  :columns="tableColumns"
                  :search="search" //过滤的条件
                  >
    </filter-table>
```
**列描述数据对象**
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
        ]
```
**下拉框选项数据格式**
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

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```
**Github源码地址**
[![](https://img.shields.io/badge/Vue%E6%BA%90%E7%A0%81%E5%9C%B0%E5%9D%80-iview--filter--table-F37F40.svg)](https://github.com/azhengyongqin/iview-filter-table)
