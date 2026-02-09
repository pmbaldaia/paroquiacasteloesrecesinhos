<script setup lang="ts">
interface Props {
  href: string;
  size?: "md" | "lg";
  block?: boolean;
  styleName?: "outline" | "primary" | "inverted" | "muted";
  className?: string;
  [x: string]: any;
}

withDefaults(defineProps<Props>(), {
  size: "lg",
  styleName: "primary",
});

const sizes = {
  lg: "px-5 py-2.5",
  md: "px-4 py-2",
};

const styles = {
  primary:
    "bg-white text-gray-800 font-semibold border border-gray-400 shadow-sm hover:bg-gray-100 hover:text-gray-900",

  outline:
    "bg-white text-gray-800 font-semibold border border-gray-400 shadow-sm hover:bg-gray-100",

  inverted:
    "bg-gray-800 text-white font-semibold border border-gray-800 hover:bg-gray-700",

  muted: "bg-gray-50 text-gray-700 border border-gray-200 hover:bg-gray-100",
};
</script>

<template>
  <NuxtLink
    :href="href"
    :class="[
      'rounded text-center transition focus-visible:ring-2 ring-offset-2 ring-gray-200',
      block && 'w-full',
      sizes[size],
      styles[styleName],
    ]"
    ><slot />
  </NuxtLink>
</template>
