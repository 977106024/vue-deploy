<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / 自动化部署测试,<br>
      check out the
    </p>
  <div id="select">
       <el-select v-model="value" clearable placeholder="请选择">
    <el-option
      v-for="item in rangeList"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
  </div>
   
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data:()=>({
    value:'',
      rangeList: [], // 围栏列表 目的地列表

  }),
  created(){
    var a = {a:1}
    var b = a?.name

    console.log(b,'ssss')
      const data = {
        typeList:[1, 2, 3],
        pageIndex: 1,
    pageSize: 10,
        }
       this.$api.post('http://localhost:8080/map/fence/getList',data).then(res => {
        const $res = res.data
        if ($res.code === 0) {
            this.rangeList = $res.data.map(item => ({
              value: item.cid,
              label: item.name
            }))
          
        }
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
/* li {
  display: inline-block;
  margin: 0 10px;
} */
a {
  color: #42b983;
}
#select{
  width: 350px;
}
</style>
