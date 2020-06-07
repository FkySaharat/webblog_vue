<template>
  <div id="all">
    <div id="side-bar"><div id="toc"></div></div>
    <div id="line"></div>
    <div id="content">
      <div id="mode">
        <button v-on:click="view=false">markdown</button>
        <button v-on:click="view=true"> result</button>
        <button >save</button>
      
      </div>
      
      <div class="container full-height">
        
        <div class="result" >
        
          <section class="" v-if="view" >
            <p v-if="source === ''">Blank ...</p>
            <vue-markdown
             id="markdown-parent"
              class="result-html full-height"
              :watches="['show','html','breaks','linkify','emoji','typographer','toc']"
              :source="source"
              :show="show"
              :html="html"
              :breaks="breaks"
              :linkify="linkify"
              :emoji="emoji"
              :typographer="typographer"
              :toc="toc"
              v-on:rendered="allRight"
              v-on:toc-rendered="tocAllRight"
              toc-id="toc"
            ></vue-markdown>
          </section>

           <div  v-else>
            <textarea   class="result" v-model="source" placeholder="Try to write something here ...">
              
            </textarea>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import axios from 'axios';
//import BlogContent from "../components/BlogContent.vue";
import VueMarkdown from "vue-markdown";
export default {
  components: {
    VueMarkdown
  },
  data() {
    return {
      source: "",
      show: true,
      html: false,
      breaks: true,
      linkify: false,
      emoji: true,
      typographer: true,
      toc: true,
      view:false,
      title:"",
      body:""
    };
  },
  methods: {
    allRight: function() {
      console.log("markdown is parsed !");
    },
    tocAllRight: function(tocHtmlStr) {
      console.log("toc is parsed :", tocHtmlStr);
    },
    watchSource: function() {
      console.log("starting with", this.source);
    },
    resize:function(){
      let textarea =document.querySelector('textarea')
      if(textarea){
         textarea.style.height='auto';
        textarea.style.height=textarea.scrollHeight+'px';
      }
     
    },
    saveTitle:function(){
      let newTitle=document.getElementById("markdown-parent");
      if(newTitle){
        console.log(newTitle.firstChild.innerHTML)
        this.title=newTitle;
      }
    },
    saveBody:function(){
      this.body=this.source;
    }
  },
  mounted() {
    console.log("mounted with", this.source);
  },
  updated() {
    this.resize()
    this.saveTitle()
    this.saveBody()
    console.log("updated", this.title);
  }
};
</script>

<style scoped>
#side-bar {
  height: 100%;
  width: 19%;
}
#content {
  height: 100%;
  width: 80%;
}
#all {
  display: flex;
  flex-wrap: wrap;
  height: 100%;
}
#result{
  width: 100%;
}
textarea{
  width: 100%;
  border: none;
  overflow: hidden;
  resize: none;
  outline: none;
}
#mode{
  display: flex;
  justify-content: flex-end;
  padding: 1rem;
}
#line{ 
  border-left: 1px solid gray;
  margin-top:50px ;
  margin-bottom: 50px;
}
</style>