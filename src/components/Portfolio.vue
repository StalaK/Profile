<template>
    <div>
        <div class="portfolio-row">
            <PortfolioBlock 
                    title="Portfolio Block 1" 
                    description="Description of work" />
                
            <PortfolioBlock 
                title="Portfolio Block 2" 
                description="Description of work" 
                titleBgColour="orange" 
                titleColour="#FF0000" />

            <PortfolioBlock 
                title="Portfolio Block 3" 
                description="Description of work" 
                descriptionbgColour="#00AA00" 
                descriptionColour="yellow" />

            <PortfolioBlock 
                title="Portfolio Block 4" 
                description="Description of work" 
                :height="150"
                :width="400" />
        </div>
    </div>
</template>

<script>
    import PortfolioBlock from './PortfolioBlock'

    export default {
        components: {
            PortfolioBlock
        }    
    }
</script>

<style scoped>

</style>