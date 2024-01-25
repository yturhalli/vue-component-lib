<template>
  <div class="vr-input-container">
    <label v-if="label">{{ label }}</label>
    <label v-if="!label">
      <slot>Please enter value:</slot>
    </label>
    <input :type="inputType" v-model="modelValue" @input="handleInput" :placeholder="placeholder" />
  </div>
</template>

<script setup>
import { defineProps, defineEmits, computed } from 'vue';

const props = defineProps(['type', 'modelValue', 'placeholder', 'label']);
const emits = defineEmits(['update:modelValue']); 

const inputType = computed(() => props.type || 'text')
const modelValue = computed({
  get: () => props.modelValue,
  set: (value) => emits('update:modelValue', value),
});

const handleInput = (event) => {
const inputValue = event.target.value;
  emits('update:modelValue', inputValue);
};
</script>

<style>
/* .vr-input-container div {
  margin-bottom: 15px;
}

.vr-input-container label {
  display: block;
  margin-bottom: 5px;
  color: #333;
}

.vr-input-container input {
  width: 100%;
  padding: 10px;
  font-size: 14px;
  border: 1px solid #87CEEB; 
  border-radius: 4px;
  box-sizing: border-box;
  transition: border-color 0.3s ease;
}

.vr-input-container input:focus {
  outline: none;
  border-color: #5a9bd5; 
} */
</style>
