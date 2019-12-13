<template>
    <div>
        <slot name="titleslot"></slot>
        <h1>I am a form Helper!</h1>
        <slot name="paraslot"></slot>
    </div>
</template>

<script>
export default {
    components: {

    }
}
</script>

<style scoped>
    h1 {
        color: red;
    }
</style>