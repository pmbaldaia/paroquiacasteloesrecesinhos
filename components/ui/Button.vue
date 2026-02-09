<script setup lang="ts">
interface Props {
  size?: "md" | "lg";
  block?: boolean;
  styleName?: "outline" | "primary" | "inverted";
  className?: string;
  [x: string]: any;
}

withDefaults(defineProps<Props>(), {
  size: "md",
  styleName: "primary",
});

const sizes = {
  md: "px-5 py-2.5",
  lg: "px-6 py-3",
};
</script>

<template>
  <button
    :class="[
      ' bg-white hover:bg-gray-100 text-gray-800 font-semibold py-2 px-4 border border-gray-400 rounded shadow',
      block && 'w-full',
      sizes[size],
      className,
    ]"
  >
    <slot />
  </button>
</template>
