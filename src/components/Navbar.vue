<template>
    <b-container>
        <b-navbar toggleable="sm">
            <b-navbar-brand to="/"><h2>Josh Hughes</h2></b-navbar-brand>
            <b-navbar-toggle target="navbar-collapse"></b-navbar-toggle>
            <b-collapse id="navbar-collapse" is-nav>
                <b-navbar-nav>
                    <b-nav-item to="/" class="link">Home</b-nav-item>
                    <b-nav-item to="/about" class="link">About</b-nav-item>
                    <b-nav-item to="/portfolio" class="link">Portfolio</b-nav-item>
                    <b-nav-item to="/contact" class="link">Contact</b-nav-item>
                </b-navbar-nav>
            </b-collapse>
        </b-navbar>
    </b-container>
</template>

<script>
</script>

<style scoped>

    .link:hover {
        text-decoration: underline;
    } 

</style>