<template>
    <div class="container">
        <header>
            <IconX @click="open = !open" class="icon"/>
        </header>
        <main>
            <ModalCustom v-if="open" @on:close="open = false">
                <template #header>
                    <h1>Header</h1>
                </template>

                <template #body>
                   <h1>main</h1>
                </template>
            </ModalCustom>
        </main>
    </div>
</template>
<script setup>
import { IconX } from '@tabler/icons-vue';
import { ref } from 'vue';
import ModalCustom from './ModalCustom.vue';

const open = ref(false)

</script>
<style lang="scss" scoped>
.container{
    width: 100vw;
    height: 100vh;
    box-sizing: border-box;
}
    header{
        background-color: blueviolet;
        height: 100px;
        width: 100vw;
    }

    main{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
    }

    .icon{
        position: absolute;
        right: 20px;
        top: 20px;
        cursor: pointer;
    }
</style>