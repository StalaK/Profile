<template>
    <b-container>
        <b-row>
            <PortfolioBlock 
                description="A website for displaying my portfolio of work"
                titleBgColour="lightblue"
                titleColour="grey"
                descriptionBgColour="white"
                descriptionColour="black">
                <div class="portfolio-block-text">Developer Profile</div>
            </PortfolioBlock>
            <PortfolioBlock 
                description="How many apocalyptic events have you survived?"
                titleBgColour="black"
                titleColour="white"
                descriptionBgColour="white"
                descriptionColour="white">
                <div class="portfolio-block-text">Am I Being Raptured?</div>
            </PortfolioBlock>

            <PortfolioBlock 
                description="Martial Arts student management"
                titleBgColour="tomato"
                titleColour="white"
                descriptionBgColour="orange"
                descriptionColour="white">
                <div class="tenko-text">TENKO</div>
            </PortfolioBlock>
            <Moodal>
                <template v-slot:launch>Moodal</template>
                <template v-slot:content>stuff</template>
            </Moodal>
        </b-row>
    </b-container>
</template>

<script>
    import PortfolioBlock from '@/components/PortfolioBlock'
    import Moodal from '@/components/Moodal'

    export default {
        components: {
            PortfolioBlock,
            Moodal
        }    
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Chango&family=Lexend+Tera&display=swap');

    .portfolio-block-text {
        font-family: 'Lexend Tera', sans-serif;
        font-style: oblique;
        padding: 10px;
    }

    .tenko-text {
        padding: 10px;
        font-family: 'Chango', cursive;
        font-size: 20pt;
    }
</style>