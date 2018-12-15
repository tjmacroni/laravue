<template id= "Viewpost">
    <div>
        <h3>{{ post.title }}</h3>
        <strong>Body : </strong>
        <div>
            {{ post.body }}
        </div>
        </br>
        <span class="glyphicon glyphicon-arrow-left"></span>
        <router-link v-bind:to="'/'">Back to Post List</router-link>
    </div>
</template>

<script>
    export default {
    data:function () {
    return {post: {title: '', body: ''}}
    },
    created: function(){
    let uri = 'http://laravue.test/post/'+this.$route.params.id;
    Axios.get(uri).then((response) => {
        this.post = response.data;
    });
    }  
    }
</script>

<style scoped>

</style>