<template>
    <div>
        <ul class="navbar-list">
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Portfolio</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>

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

</style>