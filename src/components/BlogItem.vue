<template>
  <div class="items">
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
      
      toc-id="toc"
    ></vue-markdown>
  </div>
</template>

<script>
import VueMarkdown from "vue-markdown";
export default {
  props: {
    blog: Object
  },
  data: () => {
    return {
      source: "",
      show: true,
      html: false,
      breaks: true,
      linkify: false,
      emoji: true,
      typographer: true,
      toc: true
    };
  },
  components: {
    VueMarkdown
  },
  methods:{
      allRight: function() {
      console.log("markdown is parsed !");
    },
  },
  mounted(){
      this.source=this.blog.body
  }
};
</script>

<style scoped>
.items{
    margin:2rem;
    padding: 1rem;
    width:170px;
    height:200px;
    background: burlywood;
}
</style>