<template>
    <div class="spacer">
        <div class="portfolio-block" :style="portfolioBlockStyle">
            <div class="portfolio-title">
                <span v-if="titleType == 'image'"><img :src="title" /></span>
                <span v-else>{{ title }}</span>
            </div>
            <div class="portfolio-description" :style="portfolioDescriptionStyle">
                {{ description }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            title: {
                type: String,
                required: true
            },
            titleType: {
                type: String,
                default: 'string',
                required: false
            },
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
            descriptionbgColour: {
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
                portfolioDescriptionStyle: {}
            }
        },
        mounted: function () {
            this.portfolioBlockStyle = {
                'width': `${this.width}px`,
                'height': `${this.height}px`,
                'background-color': this.titleBgColour,
                'color': this.titleColour
            };

            this.portfolioDescriptionStyle = {
                'background-color': this.descriptionbgColour,
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

    .portfolio-description {
        opacity: 50%;
        position: relative;
        top: 100%;
        height: 100%;
    }

    @keyframes display-description {
        from { top: 100%; }
        to { top: 25%}
    }

    @keyframes hide-description {
        from { top: 25%; }
        to { top: 100%; }
    }
</style>