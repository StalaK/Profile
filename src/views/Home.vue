<template>
    <b-container>
        <b-row v-for="post in pagePosts" :key="post.ID">
            <h1 v-html="post.title" class="post-title" />
            <div v-html="post.content" class="post-content" />
            <div class="post-footer">
                <i>Posted on {{ formatDate(post.date) }}.</i> 
                <i v-if="post.date !== post.modified"> Last updated: {{ formatDate(post.modified) }}</i>
            </div>
        </b-row>
        <b-row>
            <span class="previous-page" v-on:click="previousPage" v-if="currentPage > 1"><u>Newer</u></span>
            <span class="next-page" v-on:click="nextPage" v-if="currentPage < pageCount"><u>Older</u></span>
        </b-row>
    </b-container>
</template>

<script>
    import moment from 'moment'
    
    export default {
        data() {
            return {
                posts: [],
                pagePosts: [],
                pageCount: 0,
                postsPerPage: 3,
                currentPage: 1
            }
        },
        mounted: function(){
            fetch('https://public-api.wordpress.com/rest/v1.1/sites/joshhprofile.wordpress.com/posts')
                .then((response) => response.json())
                .then((responseJson) => {
                    this.posts = Array.from(responseJson.posts);
                    this.pageCount = Math.ceil(this.posts.length / this.postsPerPage);
                    this.pagePosts = this.posts.slice(0, this.postsPerPage);
                })
        },
        methods: {
            formatDate: function(date) {
                return moment(date).format('MMMM Do YYYY, HH:mm');
            },
            nextPage: function() {
                this.pagePosts = [];

                let startPost = this.currentPage * this.postsPerPage;
                let endPost = startPost + this.postsPerPage;

                this.pagePosts = this.posts.slice(startPost, endPost)
                this.currentPage += 1;
            },
            previousPage: function() {
                this.pagePosts = [];
                this.currentPage -= 1;

                let endPost = this.currentPage * this.postsPerPage;
                let startPost = endPost - this.postsPerPage;

                this.pagePosts = this.posts.slice(startPost, endPost)
            },
        }
    }
</script>

<style scoped>
    a { padding: 10px;}
    
    .post-title {
        margin: 15px 5px 15px 5px;
        text-align: center;
        color: #2f4f4f !important;
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

    .pagination {
        width: 100%;
    }

    .next-page {
        width: 50%;
        text-align: right;
        cursor: pointer;
    }

    .previous-page {
        width: 50%;
        text-align: left;
        cursor: pointer;
    }
</style>