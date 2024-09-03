<template>
  <div>
    <v-select
      :items="items"
      v-model="selectedOption"
      item-title="name"
      item-value="id"
      label="Выберите значение"
      outlined
      dense
      variant="solo"
    ></v-select>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";
const emit = defineEmits(["update:modelValue"]);
const selectedOption = ref(1);
watch(selectedOption, (newVal) => {
  emit("update:modelValue", newVal);
});

const items = ref([
  { id: 1, name: "Без сортировки" },
  { id: 2, name: "По возрастанию" },
  { id: 3, name: "По убыванию" },
]);
</script>

<style scoped></style>
