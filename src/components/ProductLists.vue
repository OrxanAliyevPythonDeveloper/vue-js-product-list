<template>
    <div>
       <p v-if="productsPropsName.length==0" class="productEmpty">Product Lists is empty!</p>
       <table v-else class="table">
           <thead>
               <tr>
                   <th>Id</th>
                   <th>Product Name</th>
                   <th>Category</th>
                   <th>About</th>
                   <th>Price</th>
                   <th>Stoks</th>
                   <th></th>
               </tr>
           </thead>
           <tbody>
               <tr v-for="product in productsPropsName" :key="product.id">
                   <td> {{ product.id }} </td>
                   <td> {{ product.categoryId }} </td>
                   <td> {{ product.productName }} </td>
                   <td> {{ product.about }} </td>
                   <td> {{ product.price }} </td>
                   <td> {{ product.stoks }} </td>
                   <td> <button class="btn btn-sm btn-danger" @click="handleDelete(product)">Delete</button> </td>
               </tr>
           </tbody>
       </table>
    </div>
</template>

<script>
export default {
    props:["productsPropsName"],
    methods:{
        handleDelete(product){
            this.$emit("delete:product",product)
        }
    }
}
</script>

<style scoped>
    .productEmpty{
        text-align: center;
        margin-top: 30px;
        background-color: red;
        font-weight: 700;
        font-size: 26px;
    }
</style>