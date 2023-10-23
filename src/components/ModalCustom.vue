<template>
    <div class="container" @click.self="$emit('on:close')">
        <slot  name="header"/>
        <slot  name="body"/>
    </div>
</template>
<script setup>
defineEmits(['on:close' ]);


</script>
<style lang="scss" scoped>
    .container{
        width: 100vw;
        height: 100vh;
        box-sizing: border-box;
        background-color: aquamarine;
    }

    
</style>