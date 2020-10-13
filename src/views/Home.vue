<template>
    <b-container>
        <b-row v-for="post in posts" :key="post.ID">
            <h1 v-html="post.title" class="post-title" />
            <div v-html="post.content" class="post-content" />
            <div class="post-footer">
                <i>Posted on {{ post.date }}.</i> 
                <i v-if="post.date !== post.modified"> Last updated: {{ post.modified }}</i>
            </div>
        </b-row>
    </b-container>
</template>

<script>
    export default {
        data() {
            return {
                posts: []
            }
        },
        mounted: function(){
            fetch('https://public-api.wordpress.com/rest/v1.1/sites/joshhprofile.wordpress.com/posts')
                .then((response) => response.json())
                .then((responseJson) => {
                    this.posts = Array.from(responseJson.posts)
                })
        }
    }
</script>

<style scoped>
    a { padding: 10px;}
    
    .post-title {
        margin: 15px 5px 15px 5px;
    }

    .post-content {
        margin: 0px 10px 0px 10px;
    }

    .post-footer{
        margin-bottom: 30px;
        margin-right: 30px;
        width: 100%;
        text-align: right;
        font-size: 0.75rem
    }
</style>