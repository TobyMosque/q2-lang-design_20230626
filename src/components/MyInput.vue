<template>
  <q-input ref="input" v-bind="props">
    <template v-for="(_, slot) in slots" :key="slot" v-slot:[slot]="scope">
      <slot :name="slot" v-bind="scope" :key="slot" />
    </template>
  </q-input>
</template>

<script setup lang="ts">
import type { QInputProps, QInputSlots } from 'quasar';
import { QInput } from 'quasar';
import { useSlots } from 'vue';

export type MyInputEmits = [
  'update:modelValue',
  'clear',
  'focus',
  'blur',
  'popupShow',
  'popupHide',
  'paste',
  'change',
  'keydown',
  'click',
  'animationend'
];
export type MyInputProps = QInputProps;
export type MyInputSlots = QInputSlots;

const emits = defineEmits(QInput['emits'] as MyInputEmits);
const slots = useSlots() as never as MyInputSlots;
const props = withDefaults(defineProps<MyInputProps>(), {
  filled: true,
});

console.log(emits, QInput['emits']);
</script>
