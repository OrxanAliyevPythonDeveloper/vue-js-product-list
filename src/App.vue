<template>
  <div>
    <ProductLists :productsPropsName="productList" @delete:product="deleteProduct" />
  </div>
</template>

<script>
import ProductLists from "./components/ProductLists"
export default {
  components:{
    ProductLists
  },
  data(){
    return{
      productList:[
        {id:"1",categoryId:"1",productName:"Acer",about:"Acer Notebook",price:"1500$",stoks:"17"},
        {id:"2",categoryId:"1",productName:"Toshiba",about:"Toshiba Notebook",price:"800$",stoks:"12"},
        {id:"3",categoryId:"1",productName:"Macbook",about:"Macbook Notebook",price:"2500$",stoks:"4"},
        {id:"4",categoryId:"2",productName:"Samsung",about:"Samsung Television",price:"1199$",stoks:"5"}
      ]
    }
  },
  methods:{
    deleteProduct(product){
      this.productList=this.productList.filter(
        productToFilter=>productToFilter.id!==product.id
      )
    }
  }
}
</script>

<style>

</style>
