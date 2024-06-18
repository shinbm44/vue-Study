<template>
    <div>
        <p class = text>{{ helloText }}</p>
    </div>
</template>
<script>
export default {
    name: "EventComponent",
    props: {
        helloText: String,
    }
}
</script>
<style>
    .text {
        background: gray;
        padding-top: 5px;
        padding-bottom: 5px;
    }
</style>