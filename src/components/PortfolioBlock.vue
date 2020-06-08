<template>
    <div class="spacer">
        <div class="portfolio-block" :style="portfolioBlockStyle">
            <div class="portfolio-title">
                <slot></slot>
            </div>
            <div class="portfolio-description" :style="portfolioDescriptionText">
                <div class="description-background" :style="portfolioDescriptionBackground"></div>
                {{ description }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            titleBgColour: {
                type: String,
                default: 'white',
                required: false
            },
            titleColour: {
                type: String,
                default: 'black',
                required: false
            },
            description: {
                type: String,
                required: true
            },
            descriptionBgColour: {
                type: String,
                default: 'black',
                required: false
            },
            descriptionColour: {
                type: String,
                default: 'white',
                required: false
            },
            width: {
                type: Number,
                default: 150,
                required: false
            },
            height: {
                type: Number,
                default: 150,
                required: false
            }
        },
        data () {
            return {
                portfolioBlockStyle: {},
                portfolioDescriptionBackground: {},
                portfolioDescriptionText: {}
            }
        },
        mounted: function () {
            this.portfolioBlockStyle = {
                'width': `${this.width}px`,
                'height': `${this.height}px`,
                'background-color': this.titleBgColour,
                'color': this.titleColour
            };

            this.portfolioDescriptionBackground = {
                'background-color': this.descriptionBgColour,
            };

            this.portfolioDescriptionText = {
                'color': this.descriptionColour
            };
        }
    }
</script>

<style scoped>
    .spacer { 
        margin: 0px 5px 5px 5px;
        display: inline-block;
    }

    .portfolio-block {
        border: 1px solid black;
        display: block;
        overflow: hidden;
        cursor: pointer;
    }

    .portfolio-block:hover .portfolio-description {
        animation-name: display-description;
        animation-duration: 0.5s;
        animation-iteration-count: 1;
        animation-fill-mode: forwards;
    }

    .portfolio-block:not(:hover) .portfolio-description {
        animation-name: hide-description;
        animation-duration: 0.5s;
        animation-iteration-count: 1;
        animation-fill-mode: forwards;
    }

    .portfolio-title {
        position: absolute;
        width: inherit;
    }

    .portfolio-description {
        position: relative;
        top: 100%;
        height: 100%;
    }

    .description-background {
        position:absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        opacity: 0.5;
    }

    @keyframes display-description {
        from { top: 100%; }
        to { top: 50% }
    }

    @keyframes hide-description {
        from { top: 50%; }
        to { top: 100%; }
    }
</style>