<template>
    <div>
        <div class="launch-slot" @click="openModal()">
            <slot name="launch"></slot>
        </div>
        <div class="overlay" :hidden="modalHidden">
            <div class="window" :hidden="modalHidden">
                <slot name="content"></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            width: {
                type: String,
                default: 'fit-content',
                required: false
            },
            height: {
                type: String,
                default: 'fit-content',
                required: false
            },
            backgroundColour: {
                type: String,
                default: 'white',
                required: false
            }
        },
        data () {
            return {
                modalHidden: true
            }
        },
        methods: {
            openModal: function() {
                this.modalHidden = !this.modalHidden;
            }
        }
    }
</script>

<style>

    .launch-slot {
        width: fit-content;
        height: fit-content;
        cursor: pointer;
    }

    .overlay {
        width: 100%;
        height: 100%;
        background-color:rgba(0, 0, 0, 0.25);
        position: absolute;
    }

    .window {
        width: fit-content;
        height: fit-content;
        background-color: rgba(255, 255, 255, 1);
        margin: 15px;
        padding: 15px;
        border-radius: 15px;
    }

</style>