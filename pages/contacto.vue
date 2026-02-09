<script setup>
definePageMeta({
  layout: "landing",
});
</script>

<template>
  <UiContainer>
    <UiSectionhead>
      <template #title>Contacto</template>
      <template #desc>
        Utilize o formulário abaixo para enviar a sua mensagem.
      </template>
    </UiSectionhead>

    <div class="mx-auto max-w-3xl mt-10">
      <LandingContactform />
    </div>
  </UiContainer>
</template>
