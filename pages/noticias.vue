<script setup>
definePageMeta({
  layout: "landing",
});
</script>

<template>
  <UiContainer>
    <UiSectionhead>
      <template #title>Notícias</template>
      <template #desc>
        Acompanhe as novidades, comunicados e iniciativas da paróquia.
      </template>
    </UiSectionhead>

    <div class="mt-12 max-w-3xl mx-auto text-slate-700">
      <div
        class="border border-dashed border-slate-300 rounded-lg px-6 py-10 text-center bg-slate-50"
      >
        <h2 class="text-base font-semibold text-gray-800">
          Em breve serão partilhadas notícias.
        </h2>
        <p class="mt-3 text-sm">
          Esta página será atualizada com notícias da vida da comunidade,
          iniciativas pastorais, eventos, avisos e informações importantes sobre
          as obras de restauro da Igreja.
        </p>
      </div>
    </div>
  </UiContainer>
</template>

