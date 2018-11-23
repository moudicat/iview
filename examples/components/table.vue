<template>
  <div>
    <Button @click="handlecc">aaaaa</Button>
    <Button @click="handlehh">hhhhh</Button>
    <Button @click="handleaa">ccccc</Button>

    <Table ref="table" width="750" border :columns="columns2" :data="data3"></Table>
  </div>
</template>
<script>
export default {
  name: 'etable',
  data() {
    return {
      columns2: [
        {
          type: 'selection',
          width: 60,
          align: 'left',
          sortable: true
        },
        {
          title: '姓名',
          key: 'name',
          width: 100,
          sortable: 'pinyin'
        },
        {
          title: '年龄',
          key: 'age',
          width: 100
        },
        {
          title: '省份',
          key: 'province',
          width: 100
        },
        {
          title: '市区',
          key: 'city',
          width: 100
        },
        {
          title: '地址',
          key: 'address',
          width: 200
        },
        {
          title: '邮编',
          key: 'zip',
          width: 100
        },
        {
          title: '操作',
          key: 'action',
          fixed: 'right',
          width: 120,
          render: (h, params) => {
            return h('div', [
              h(
                'Button',
                {
                  props: {
                    type: 'text',
                    size: 'small'
                  }
                },
                '查看'
              ),
              h(
                'Button',
                {
                  props: {
                    type: 'text',
                    size: 'small'
                  }
                },
                '编辑'
              )
            ]);
          }
        }
      ],
      data3: [
        {
          name: '币王小明',
          age: 18,
          address: '北京市朝阳区芍药居',
          province: '北京市',
          city: '朝阳区',
          zip: 100000
        },
        {
          name: '哎张小刚',
          age: 25,
          address: '北京市海淀区西二旗',
          province: '北京市',
          city: '海淀区',
          zip: 100000
        },
        {
          name: '第李小红',
          age: 30,
          address: '上海市浦东新区世纪大道',
          province: '上海市',
          city: '浦东新区',
          zip: 100000
        },
        {
          name: '诶周小伟',
          age: 26,
          address: '深圳市南山区深南大道',
          province: '广东',
          city: '南山区',
          zip: 100000
        },
        {
          name: '总经理'
        },
        {
          name: '预算分析专员'
        }
      ]
    };
  },
  mounted() {
    console.log(1);
  },
  methods: {
    handlecc() {
      this.$refs.table.selectedFixToTop('name');
    },
    handlehh() {
      this.$refs.table.stopWatch();
      this.$set(this.data3[2], '_hidden', true);
    },
    handleaa() {
      this.$set(this.data3[2], '_hidden', false);
    }
  } 
};
</script>
