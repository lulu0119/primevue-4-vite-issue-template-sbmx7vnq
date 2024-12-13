<template>
    <div class="card flex justify-center">
        <InputText type="text" v-model="value" @keydown="onKeydown" @keypress="onKeypress" />
    </div>
    <div class="flex flex-col justify-center items-center gap-2 mt-8">
        <div>keydown: {{ keydownEvent }}</div>
        <div>keypress: {{ keypressEvent }}</div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const value = ref(null);

const keydownEvent = ref(null);
const keypressEvent = ref(null);
const onKeydown = (event) => {
    keydownEvent.value = JSON.stringify({ key: event.key, code: event.code });
};

const onKeypress = (event) => {
    keypressEvent.value = JSON.stringify({ key: event.key, code: event.code });
};
</script>
