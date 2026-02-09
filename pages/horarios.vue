<script setup>
definePageMeta({
  layout: "landing",
});
</script>

<template>
  <UiContainer>
    <UiSectionhead>
      <template #title>Horários</template>
      <template #desc>
        Missas, celebrações e outros momentos de oração na paróquia.
      </template>
    </UiSectionhead>

    <div
      class="mt-12 grid gap-8 md:grid-cols-2 max-w-3xl mx-auto text-slate-700"
    >
      <section>
        <h2 class="text-lg font-semibold text-gray-800">
          Missas dominicais
        </h2>
        <p class="mt-2">
          Em breve serão publicados aqui os horários atualizados das missas de
          domingo e dias santos na Paróquia de Castelões de Recesinhos.
        </p>
      </section>

      <section>
        <h2 class="text-lg font-semibold text-gray-800">
          Missas feriais e outros momentos
        </h2>
        <p class="mt-2">
          Também poderá encontrar nesta página os horários de missas durante a
          semana, adoração, recitação do terço e outros momentos de oração
          comunitária.
        </p>
      </section>

      <section class="md:col-span-2">
        <div class="rounded-lg border border-slate-200 bg-slate-50 p-4">
          <p class="text-sm">
            Para confirmar um horário específico, contacte a paróquia através
            da página de
            <a href="/contacto" class="underline hover:text-slate-900">
              contacto
            </a>
            .
          </p>
        </div>
      </section>
    </div>
  </UiContainer>
</template>

