<template>
  <div id="show-blogs">
    <h1>Show - Blogs</h1>
    <div v-for="blog in blogs" class="single-blog">
        <h2>{{blog.title}}</h2>
        <article>
            {{blog.body}}
        </article>
    </div>
  </div>
</template>

<script>
export default {
  name: 'show-blogs',
  data(){
      return{
        blogs:[]
      }
  },
  created(){
      this.$http.get('http://localhost:8888/blogs').then(function(data){
          console.log(data)
          this.blogs = data.body.slice(0,9);
          console.log(this.blogs)
      })
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
}
</style>
