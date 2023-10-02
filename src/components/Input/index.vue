<template>
  <label class="formLabel">
    {{ labelText }}
    <input placeholder="Escribir" :type="type" :value="value" @input="updateValue" />
  </label>
</template>

<script setup>
defineProps({
  labelText: {
    required: true,
    default: 'Texto'
  },
  type: String,
  value: String,
})

const emit = defineEmits(['update:value']);

const updateValue = (event) => {
  const text = event.target.value;
  emit('update:value', text);
};
</script>

<style scoped>
.formLabel {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 10px;
}

.formLabel input {
  padding: 6px;
  border-radius: 4px;
  border: 1px solid gray;
}
</style>