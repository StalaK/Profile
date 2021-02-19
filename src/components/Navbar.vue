<template>
    <b-container class="header">
        <b-navbar toggleable="sm" variant="faded">
            <b-navbar-toggle target="navbar-collapse">
                <h2 class="title">Josh Hughes</h2>
            </b-navbar-toggle>
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

<style>

    .navbar-toggler {
        border-color: none !important;
        border: none !important;
    }
    .title {
        color: #c0c0c0;
        border: none !important;
    }

    .link {
        color: #c0c0c0 !important;
        font-size: 24pt;
    }

    nav .navbar-nav li a {
        color: #c0c0c0 !important;
    }

    .link:hover {
        text-decoration: underline;
    } 

</style>