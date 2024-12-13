<template>
  <div class="card flex justify-center">
    <InputText type="text" v-model="value" @keydown="onKeydown" />
  </div>
  <div>
    {{ eventObject }}
  </div>
</template>

<script setup>
import { ref } from 'vue';

const value = ref(null);

const eventObject = ref(null);

const onKeydown = (event) => {
  eventObject.value = JSON.stringify({ key: event.key, code: event.code });
};
</script>
