<template>
  <button :class="buttonClass">
    <slot />
  </button>
</template>

<script setup>
import { cva } from "class-variance-authority";
import { computed } from "vue";

const props = defineProps({
  variant: {
    type: String,
    validator(value) {
      return [
        "default",
        "destructive",
        "outline",
        "subtle",
        "ghost",
        "link",
        "icon",
        "iconCircle",
        "loading"
      ].includes(value);
    },
    default: "default",
  },
});

const buttonClass = computed(() => {
  return cva(
    " flex items-center justify-center font-medium transition-all font-main",
    {
      variants: {
        variant: {
          default: "text-white px-4 py-2 bg-slate-900 rounded-md hover:bg-slate-700",
          destructive: "text-white px-4 py-2 bg-red-500 rounded-md hover:bg-red-600",
          outline: "border bg-white px-4 py-2 text-slate-900 rounded-md hover:bg-slate-100",
          subtle: "bg-slate-100 px-4 py-2 text-slate-900 rounded-md hover:bg-slate-200",
          ghost: "text-slate-900 px-4 py-2 rounded-md hover:bg-slate-100",
          link: "text-slate-900 px-4 py-2 rounded-md hover:underline hover:decoration-[1.5px]",
          icon: "p-2 text-slate-900 border rounded-md hover:bg-slate-100",
          iconCircle: "rounded-full p-2 text-slate-900 border hover:bg-slate-100",
          loading: "bg-slate-900 bg-opacity-50 px-4 py-2 rounded-md text-white",
          disabled: "bg-slate-500 text-white rounded-md px-4 py-2"
        },
      },
    }
  )({
    variant: props.variant,
  });
});
</script>
