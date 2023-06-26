<template>
  <q-page class="row items-center justify-evenly">
    <my-input label="Text" v-model="text" @>
      <template v-slot:append>
        <q-avatar>
          <img src="https://cdn.quasar.dev/logo-v2/svg/logo.svg" />
        </q-avatar>
      </template>
    </my-input>
  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const text = ref('Hello');
</script>
