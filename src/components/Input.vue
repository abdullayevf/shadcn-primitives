<template>
  <div>
    <label v-if="label" :for="id">
      {{ label }}
    </label>
    <input
      :id="id"
      :type="type"
      :placeholder="placeholder"
      :disabled="disabled"
      v-model="inputValue"
      class="px-3 py-2 font-normal border rounded-md outline-none text-slate-900 focus:ring-2 focus:ring-slate-400 focus:ring-offset-2 border-slate-300 placeholder:text-slate-400 disabled:placeholder:text-slate-300"
    />
  </div>
</template>

<script setup>
const props = defineProps({
  id: {
    type: String,
    default: "email",
  },
  type: {
    type: String,
    default: "text",
  },
  label: String,
  placeholder: String,
  disabled: Boolean,
});

const inputValue = defineModel();
</script>
