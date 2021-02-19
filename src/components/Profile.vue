<template>
    <b-container class="profile">
        <b-container>
            <img class="profile-picture" src="../../public/img/profile.jpg">
        </b-container>
        <b-container class="header">
            <b-navbar-brand to="/" class="header-link"><h1>Josh Hughes</h1></b-navbar-brand>
        </b-container>
        <b-container class="tagline">
            Full stack .NET dev from Leeds, UK
        </b-container>
    </b-container>
</template>

<style scoped>

    .profile {
        text-align: center;
    }

    img {
        border-radius: 50%;;
    }

    .portfolio {
        text-align: center;
    }

    .header {
        color: #2f4f4f !important;
        margin-top: 10px;
    }

    .header-link {
        text-decoration: none;
        color: #2f4f4f !important;
    }

    .tagline {
        color: #666666 !important;
    }

</style>