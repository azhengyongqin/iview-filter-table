<template>
  <div class="hello">
    <filter-table @load="loadData"
                  :data="users"
                  :columns="tableColumns"
                  :search="search">
    </filter-table>
  </div>
</template>

<script>
  import FilterTable from './FilterTable';

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

  const users = [
    {
      username: '小明',
      phone: '17760172601',
      email: '1023007219@qq.com',
      money: '50',
      status: '1',
    }, {
      username: '小兰',
      phone: '17760172605',
      email: '1023007219@qq.com',
      money: '50',
      status: '2',
    }, {
      username: '小东',
      phone: '17761232601',
      email: '1023007219@qq.com',
      money: '20',
      status: '2',
    }, {
      username: '咱三',
      phone: '17722226011',
      email: '1023007219@qq.com',
      money: '20',
      status: '1',
    }, {
      username: '小明',
      phone: '17760202601',
      email: '1023007219@qq.com',
      money: '20',
      status: '1',
    }, {
      username: '尼斯',
      phone: '17760172601',
      email: '1023007219@qq.com',
      money: '50',
      status: '1',
    }, {
      username: '导航',
      phone: '17760172601',
      email: '1023007219@qq.com',
      money: '20',
      status: '1',
    }, {
      username: '但是还是',
      phone: '17760172601',
      email: '1023007219@qq.com',
      money: '50',
      status: '1',
    },
  ];

  export default {
    name: 'HelloWorld',
    components: {FilterTable},

    data() {
      return {
        search: {},
        users: [],
        tableColumns: [
          {
            title: '用户名',
            key: 'username',
            filter: {
              type: 'Input'
            }
          },
          {
            title: '手机号',
            key: 'phone',
            filter: {
              type: 'Input'
            }
          },
          {
            title: '邮箱',
            key: 'email',
            filter: {
              type: 'Input'
            }
          },
          {
            title: '账户余额 (元)',
            key: 'money',
            filter: {
              type: 'Input'
            },
          },
          {
            title: '状态',
            key: 'status',
            filter: {
              type: 'Select',
              option: userStatus
            },
            render: (h, params) => {
              return h('Tag', {
                slot: 'context',
                props: {
                  color: this.formatStatus(params.row.status, userStatus).color
                }
              }, this.formatStatus(params.row.status, userStatus).name)
            }
          },

        ],
      }
    },
    async mounted() {
      await this.loadData();
    },
    methods: {

      /**
       * 格式化状态
       * @param value 状态值
       * @param status 状态对象
       * @returns {*} 返回状态
       */
      formatStatus(value, status) {
        return status[value] || {value: '', name: ''};
      },
      loadData() {
        //模拟数据库查询数据
        this.users = users;
        //这个search应该是传到后台,然后台来根据条件查询数据库
        console.log('查询条件',this.search);
      }
    },

  }
</script>

<style scoped>

</style>
