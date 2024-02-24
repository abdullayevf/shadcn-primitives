<template>
  <form class="space-y-2">
    <div class="flex space-x-2">
      <Input v-model="inputValue" :disabled="props.disabled"></Input>

      <Button
        :disabled="props.disabled"
        :variant="props.disabled ? 'disabled' : 'default'"
        >Subscribe</Button
      >
    </div>

    <p class="text-sm font-normal text-slate-500">Enter your email address</p>
  </form>
</template>

<script setup>
import Button from "./Button.vue";
import { ref } from "vue";
import Input from "./Input.vue";

const props = defineProps({
  disabled: {
    type: Boolean,
    default: false,
  },
});

const inputValue = ref("");
</script>
