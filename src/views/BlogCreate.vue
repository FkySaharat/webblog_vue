<template>
  <div>
    <div class="create">
      create blog
      <div id="demo" contenteditable="true"></div>
      <b-button variant="success" style="margin-top:0.2rem" v-on:click="createblog">create</b-button>
    </div>
    <div class="result">
      result:
      <pre>{{content}}</pre>
      
       
      
      <div id=md2>
        <blog-content  :contentmd="content"></blog-content>
      </div>
     
    </div>
  </div>
</template>

<script>

import { BButton } from "bootstrap-vue";
import BlogContent from "../components/BlogContent.vue";
export default {
  components: {
    "b-button": BButton,
    "blog-content": BlogContent,
    
  },
  data() {
    return {
      content:"testttt"
        
    };
  },
  computed:{
    // content:function(){
    //   return ;
    // }
  },
  methods: {
    createblog: function() {
        
      let newContent = document.getElementById("demo").innerHTML;
      if (this.content != newContent) {  
        this.content = newContent;
        console.log(this.content);
      }
      // return newContent

    }
  },



};
</script>

<style>
</style>