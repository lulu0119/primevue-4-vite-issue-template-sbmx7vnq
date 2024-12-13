<template>
    <div class="card flex justify-center items-center flex-col gap-2">
        <div class="flex flex-col gap-2">
            <label for="input-text">Input Text</label>
            <InputText
                id="input-text"
                type="text"
                v-model="value"
                @keydown="onKeydown"
                @keypress="onKeypress"
            />
        </div>
        <div class="flex flex-col gap-2">
            <label for="input-number">Input Number</label>
            <InputNumber
                id="input-number"
                type="number"
                v-model="valueNumber"
                @keydown="onKeydown"
                @keypress="onKeypress"
            />
        </div>
    </div>
    <div class="flex flex-col justify-center items-center gap-2 mt-8">
        <div>keydown:</div>
        <div class="text-sm">{{ keydownEvent }}</div>
        <div>keypress:</div>
        <div class="text-sm">{{ keypressEvent }}</div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const value = ref("Hello World");
const valueNumber = ref(2351.35);

const keydownEvent = ref(null);
const keypressEvent = ref(null);
const onKeydown = (event) => {
    keydownEvent.value = JSON.stringify({ key: event.key, code: event.code });
};

const onKeypress = (event) => {
    keypressEvent.value = JSON.stringify({ key: event.key, code: event.code });
};
</script>
