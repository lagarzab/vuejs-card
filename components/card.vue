<template>
    <div class='card--container' :style='cardStyle'>
        <div :style='headerStyle'>
            <slot name='header'></slot>
        </div>
        <div class='default' :style='contentStyle'>
            <slot name='default'></slot>
        </div>
        <div :style='footerStyle'>
            <slot name='footer'></slot>
        </div>
        <a v-if='link' :href='link'><div class='hover--layer'></div></a>
        <div v-else class='hover--layer'></div>
    </div>
</template>

<script>
export default {
    name: 'card',
    props: {
        height: {
            type: Number,
            default: 350
        },
        width: {
            type: Number,
            default: 250
        },
        blurReverse: {
            type: Boolean,
            default: false
        },
        headerStyle: {
            type: String,
            default: ''
        },
        contentStyle: {
            type: String,
            default: ''
        },
        footerStyle: {
            type: String,
            default: ''
        }
    },
    computed: {
        alphaCardHover () {
            return this.blurReverse ? '0' : '.5'
        },
        alphaCardStill () {
            return this.blurReverse ? '.5' : '0'
        },
        cardStyle () {
            return {
                'height': this.height + 'px',
                'width': this.width + 'px'
            }
        }
    },
    created () {
        document.documentElement.style.setProperty('--card-alpha-still', this.alphaCardStill)
        document.documentElement.style.setProperty('--card-alpha-hover', this.alphaCardHover)
    }
}
</script>

<style lang='scss'>
    .card--container {
        display: inline-flex;
        flex-direction: column;
        justify-content: space-between;
        position: relative;
        padding: 4px;
        margin: 5px;
        text-align: center;
        border: 1px solid;
        border-radius: 5px;
    }
    .card--container footer{
        vertical-align: bottom;
    }
    .card--container .default {
        flex: 1 0 auto;
        display:flex;
        flex-direction: column;
        justify-content: center;
        align-content: center;
    }
    .hover--layer {
        position: absolute;
        left:0;
        right: 0;
        top: 0;
        bottom: 0;
        background-color: rgba(169, 169, 169, var(--card-alpha-still));
    }
    .hover--layer:hover {
        background-color: rgba(169, 169, 169, var(--card-alpha-hover));
    }
</style>
