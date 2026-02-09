<script setup>
definePageMeta({
  layout: "landing",
});
</script>

<template>
  <UiContainer>
    <UiSectionhead>
      <template #title>Sacramentos</template>
      <template #desc>
        Informação geral sobre os sacramentos na Paróquia de Castelões de
        Recesinhos.
      </template>
    </UiSectionhead>

    <div class="mt-12 grid gap-8 md:grid-cols-2 max-w-4xl mx-auto text-slate-700">
      <section>
        <h2 class="text-lg font-semibold text-gray-800">Batismo</h2>
        <p class="mt-2">
          Para preparar o Batismo, é necessário um tempo de catequese e
          acompanhamento das famílias. Em breve será disponibilizada informação
          mais detalhada sobre datas e preparação.
        </p>
      </section>

      <section>
        <h2 class="text-lg font-semibold text-gray-800">Primeira Comunhão</h2>
        <p class="mt-2">
          A preparação para a Primeira Comunhão é feita através da catequese
          paroquial, ao longo de vários anos, ajudando as crianças a crescer na
          fé e na participação na Eucaristia.
        </p>
      </section>

      <section>
        <h2 class="text-lg font-semibold text-gray-800">Crisma</h2>
        <p class="mt-2">
          O Crisma confirma e fortalece a fé recebida no Batismo. Os percursos
          de preparação são organizados periodicamente na paróquia.
        </p>
      </section>

      <section>
        <h2 class="text-lg font-semibold text-gray-800">Matrimónio</h2>
        <p class="mt-2">
          Os noivos que desejem celebrar o Matrimónio na paróquia devem
          contactar com antecedência para marcar a data e tratar da preparação
          necessária.
        </p>
      </section>

      <section class="md:col-span-2">
        <div class="rounded-lg border border-slate-200 bg-slate-50 p-4">
          <p class="text-sm">
            Para qualquer sacramento, recomendamos que entre em contacto com a
            paróquia através da página de
            <a href="/contacto" class="underline hover:text-slate-900">
              contacto
            </a>
            , para esclarecer dúvidas e combinar os passos a seguir.
          </p>
        </div>
      </section>
    </div>
  </UiContainer>
</template>

