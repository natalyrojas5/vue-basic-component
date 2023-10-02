<template>
  <div class="form">
    <h1>Formulario</h1>
    <Input labelText="Nombre" type="text" v-model:value="user.name" />
    <Input labelText="Apellido" type="text" v-model:value="user.lastname" />
    <Input labelText="Edad" type="number" v-model:value.number="user.age" />
    <br />
    <pre>
      <code>{{ JSON.stringify(user, null, 3) }}</code>
    </pre>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Input from '@/components/Input/index.vue';

const user = ref({
  name: '',
  lastname: '',
  age: '',
});
</script>

<style scoped>
.form {
  max-width: 400px;
  margin: auto;
}

.form h1 {
  font-weight: 600;
  margin-bottom: 16px;
}
</style>