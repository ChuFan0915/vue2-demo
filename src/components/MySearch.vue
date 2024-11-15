<template>
  <div class="container">
    <h3>Github,Search Users </h3>
    <div>
        <input type="text" placeholder="search for your name" v-model="keywords">
        <button @click="getNames">Search</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
    data() {
        return {
            keywords:''
        }
    },
    methods:{
        getNames(){
            axios.get(`https://api.github.com/search/users?q=${this.keywords}`).then(
                Response=>{
                    console.log('请求成功了',Response.data);
                    this.$bus.$emit('getUsers',Response.data.items)
                },
                error=>{
                    console.log('请求失败了',error.message);

                }
            )
            
        }
    }

}
</script>

<style>
.container{
    display: flex;
    justify-content: center;
    flex-direction: column;
    background-color: #ccc;
    padding-left: 10px;
}
</style>