<template>
    <b-container>
        <b-row>
            <PortfolioBlock 
            description="A website for displaying my portfolio of work"
            titleBgColour="lightblue"
            titleColour="grey">
                <div class="developer-profile-text">Developer Profile</div>
            </PortfolioBlock>
        </b-row>
    </b-container>
</template>

<script>
    import PortfolioBlock from '@/components/PortfolioBlock'

    export default {
        components: {
            PortfolioBlock
        }    
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Lexend+Tera&display=swap');

    .developer-profile-text {
        font-family: 'Lexend Tera', sans-serif;
        font-style:oblique;
        padding: 10px;
    }
</style>