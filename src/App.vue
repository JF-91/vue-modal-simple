<script setup>
import ExampleComponent from './components/ExampleComponent.vue';
import {ref} from 'vue';
import ModalCustom from './components/ModalCustom.vue';
import { IconX } from '@tabler/icons-vue';
const open = ref(false)

defineEmits(['on:close']);

const closeModal = () => {
    open = false;
}

</script>

<template>

    <!-- <ExampleComponent v-if="open"/> -->

    <div class="button-container"  >

        <button @click="open = !open">here link</button>
        <ModalCustom v-if="open" @on:close="open = false" @keydown.esc="closeModal">
            <template #header>
                <header>
                    <IconX @click="open = !open" class="icon"/>
                </header>
            </template>
            <template #body>
                <h1>main</h1>
            </template>
        </ModalCustom>
    </div>

</template>

<style scoped>

.button-container{
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
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
