<template>
  <div v-theme:column="'narrow'" id="show-blogs">
    <h1>博客总览</h1>
    <input type="text" v-model="search" placeholder="搜索">
    <div v-for="blog in filteredBlogs" class="single-blog">
        <router-link v-bind:to="'blog/' + blog.id"><h2 v-rainbow >{{blog.title | to-uppercase}}</h2></router-link>
        <article>
            {{blog.body | snippet}}
        </article>
    </div>
  </div>
</template>

<script>
export default {
  name: 'show-blogs',
  data(){
      return{
        blogs:[],
        search:"JS",
      }
  },
  created(){
      this.$http.get('http://localhost:8888/blog/get/0').then(function(data){
          console.log(data)
          this.blogs = data.body.slice(0,10);
      })
  },
  computed:{
    filteredBlogs:function(){
      return this.blogs.filter((blog) =>{
        return blog.title.match(this.search)
      })
    }
  },
  filters:{
    // "to-uppercase":function(value){
    //   return value.toUpperCase();
    // }
    // toUppercase(value){
    //   return value.toUpperCase();
    // }
  },
  directives:{
    // 'rainbow':{
    //   bind(el,binding,vnode){
    //     el.style.color = "#"+Math.random().toString(16).slice(2,8);
    //   }
    // }
  }
}
</script>

<style>
#show-blogs{
    max-width: 800px;
    margin: 0 auto;
}

.single-blog{
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background: #eee;
    border: 1px dotted #aaa;
}

#single-blog a{
    color: #444;
    text-decoration: none;
}

input[type="text"]{
  padding: 18px;
  width: 100%;
  box-sizing: border-box;
}
</style>
