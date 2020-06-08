<template>
  <div class="home">
    <div class="d-flex flex-wrap">
      <div v-for="(item) in listBlog" :key="item.index" >
       
        <blog-item :blog="{title:item.title,body:item.body}" ></blog-item>
      </div>
    </div>
    
  </div>
</template>

<script>

const STORAGE_KEY ='blog-storage'

import BlogItem from '../components/BlogItem.vue'
export default {
    data:()=>{
      return{
        listBlog:[]
      }
    },
    components:{
      BlogItem
    },
    methods:{
      
    },
    mounted(){
      this.listBlog =JSON.parse(localStorage.getItem(STORAGE_KEY) || '[]')
    }
}
</script>
