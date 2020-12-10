<template>
  <div class="hello">
    <input type="button" @click="cartList" value="请求">
    <div id="m-con" style="display:none"></div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods:{
    cartList(){
      console.log(111)
      let th = this;
      this.$axios.get('/api/zh-CN/products?utf8=✓&q%5Bterminal1_min_eq%5D=0&q%5Bterminal2_min_eq%5D=0&q%5Bterminal3_min_eq%5D=0&q%5Bkeywords_search%5D=&q%5Btaxons_id_eq%5D=&q%5Bbrand_id_eq%5D%5B%5D=&q%5Bbrand_id_eq%5D%5B%5D=171&q%5Bbrand_id_eq%5D%5B%5D=&q%5Bmaster_prices_between%5D=&q%5Blimited_eq%5D=0&q%5Banchor_taxons_id_eq%5D=')
      .then(function (response) {
        let dom = th.parseDom(response.data);
        let goods1 = document.getElementById("product_319464");
        let goods2 = document.getElementById("product_319468");
        let goods3 = document.getElementById("product_319470");
        if(goods1.getElementsByClassName("cart").length>0){
          
        }
      })
      .catch(function (error) {
        console.log(error);
      });
    },
    parseDom(arg) {

　　 var objE = document.getElementById("m-con");

　　 objE.innerHTML = arg;

　　 return objE.childNodes;

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
