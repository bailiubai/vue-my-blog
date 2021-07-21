<template>
    <div id="single-blog" class="single-blog">
        <h1> {{blog.title}} </h1>
        <article> {{blog.body}} </article>
    </div>
</template>

<script>
export default {
    name:"single-blog",
    data(){
        return{
            id:this.$route.params.id,
            blog:{}
        }
    },
    created(){
        
        this.$http.get('http://localhost:8888/blog/get/' + this.id).then(function(data){
            this.blog = data.data[0];
            console.log(this.blog);
        })
    }
}
</script>

