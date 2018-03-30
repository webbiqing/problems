<template>
  <div id="app">
    <el-select v-model="value8" filterable placeholder="请选择" :filter-method="testSearch">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value"
      >
      </el-option>
    </el-select>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data(){
      /*
      * options 就是
       */
      return{
        options: [{
          value:'选项1',
          label:'黄金糕'
        }, {
          value:'选项2',
          label:'双皮奶'
        }],
        searchData:[{
          value:'选项1',
          label:'黄金糕'
        }, {
          value:'选项2',
          label:'双皮奶'
        }, {
          value:'选项3',
          label:'蚵仔煎'
        }, {
          value:'选项4',
          label:'龙须面'
        }, {
          value:'选项5',
          label:'北京烤鸭'
        }],
        value8:''
      }
    },
    methods:{
      testSearch(query){
        if(query != ''){
          this.options = this.searchData.filter(item => {
            console.log(item.label.indexOf(query) > -1);
            return item.label.indexOf(query) > -1
          })
          console.log(this.options)
        }else{
          //这里取你需要的Top20
        }
      }
    }
  }
</script>

