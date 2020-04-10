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
        cardStyle () {
            return {
                'height': this.height + 'px',
                'width': this.width + 'px'
            }
        }
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
</style>
