<template>
    <div>
        <ul class="navbar-list">
            <li><a @click="NavigateTo('home')">Home</a></li>
            <li><a @click="NavigateTo('about')">About</a></li>
            <li><a @click="NavigateTo('portfolio')">Portfolio</a></li>
            <li><a @click="NavigateTo('contact')">Contact</a></li>
        </ul>
    </div>
</template>

<script>
    export default {
        methods: {
            NavigateTo: function (page) {
                this.$emit('navigate', page);
            }
        }
    }
</script>

<style scoped>

    a {
        cursor: pointer;
        font-size: larger;
    }

    a:link {
        color: black;
        text-decoration: none;
    }

    a:visited {
        color: gray;
        text-decoration: none;
    }

    a:hover {
        text-decoration: underline;
    }

    .navbar-list {
        list-style: none;
        margin: 0;
        padding: 0;
    }

    li {
        margin-top: 5px;
        margin-bottom: 5px;
    }

</style>