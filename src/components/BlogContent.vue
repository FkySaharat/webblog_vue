<template>
    <div>
    
        <vue-markdown>{{contentmd}}</vue-markdown> 
    </div>
</template>

<script>
import VueMarkdown from 'vue-markdown'
export default {
    name:"BlogContent",
    props:[
        'contentmd',
        
    ],
    components:{
        VueMarkdown,
    },
    data:function(){
        return{
            source: new Date().toLocaleTimeString(),
            
           
        }
    },
    mounted () {
        setInterval(() => {
          this.source = new Date().toLocaleTimeString();
        }, 1000);
      }
   
}
</script>

<style>

</style>