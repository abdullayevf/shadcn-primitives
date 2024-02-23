<template>
  <label for="email" :class="labelClass">Email</label>
  <form class="flex space-x-2">
    <input
      type="text"
      placeholder="Email"
      :disabled="props.variant === 'disabled' ? true : false"
      class="px-3 py-2 font-normal border rounded-md outline-none text-slate-900 focus:ring-2 focus:ring-slate-400 focus:ring-offset-2 border-slate-300 placeholder:text-slate-400 disabled:placeholder:text-slate-300"
    />
    <Button
      :disabled="props.variant === 'disabled' ? true : false"
      :variant="props.variant === 'disabled' ? 'disabled' : 'default'"
      >Subscribe</Button
    >
  </form>
  <p class="text-sm font-normal text-slate-500">Enter your email address</p>
</template>

<script setup>
import Button from "./Button.vue";
import { cva } from "class-variance-authority";
import { computed } from "vue";

const variant = "disabled";

const props = defineProps({
  variant: {
    type: String,
    validator(value) {
      ["active", "disabled"].includes(value);
    },
    default: "active",
  },
});

const labelClass = computed(() => {
  return cva("text-sm font-medium", {
    variants: {
      variant: {
        active: "text-slate-900",
        disabled: "text-slate-500",
      },
    },
  })({
    variant: props.variant,
  });
});
</script>
