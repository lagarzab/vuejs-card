<template>
    <div class='card--container'>
        <div>
            <slot name='header'></slot>
        </div>
        <div>
            <slot name='default'></slot>
        </div>
        <div>
            <slot name='footer'></slot>
        </div>
    </div>
</template>

<script>
export default {
    name: 'card'
}
</script>

<style lang='scss' scoped>
    .card--container {
        display: inline-flex;
        flex-direction: column;
        justify-content: space-between;
        position: relative;
        height: 350px;
        width: 250px;
        padding: 4px;
        margin: 5px;
        text-align: center;
        border: 1px solid;
        border-radius: 5px;
    }
    .card--container footer{
        vertical-align: bottom;
    }

    .card--container div:first-of-type {
        flex: 1 0 auto;
        display:flex;
        flex-direction: column;
        justify-content: center;
        align-content: center;
    }
</style>
