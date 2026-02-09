<script setup>
definePageMeta({
  layout: "landing",
});
</script>

<template>
  <UiContainer>
    <UiSectionhead>
      <template #title>Apoio</template>
      <template #desc>
        Formas simples de apoiar a vida da comunidade e as obras de restauro.
      </template>
    </UiSectionhead>

    <div class="mt-12 grid gap-8 md:grid-cols-3 max-w-5xl mx-auto">
      <section class="rounded-2xl border border-slate-200 p-6 bg-white">
        <h2 class="text-lg font-semibold text-gray-800">Donativo pontual</h2>
        <p class="mt-2 text-sm text-slate-600">
          Pode contribuir com um donativo para apoiar as obras de restauro e a
          manutenção da Paróquia de Castelões de Recesinhos.
        </p>
        <p class="mt-4 text-xs text-slate-500">
          Os dados para donativo serão partilhados localmente na paróquia ou
          através de contacto direto.
        </p>
      </section>

      <section class="rounded-2xl border border-slate-200 p-6 bg-white">
        <h2 class="text-lg font-semibold text-gray-800">
          Contribuição regular
        </h2>
        <p class="mt-2 text-sm text-slate-600">
          A contribuição regular ajuda a assegurar as despesas correntes da
          comunidade e o acompanhamento pastoral ao longo de todo o ano.
        </p>
        <p class="mt-4 text-xs text-slate-500">
          Em breve será disponibilizada informação mais detalhada sobre formas
          de contribuição periódica.
        </p>
      </section>

      <section class="rounded-2xl border border-slate-200 p-6 bg-white">
        <h2 class="text-lg font-semibold text-gray-800">Voluntariado</h2>
        <p class="mt-2 text-sm text-slate-600">
          O seu tempo e disponibilidade são também uma forma de apoio. Há
          várias áreas em que pode ajudar na vida da paróquia.
        </p>
        <p class="mt-4 text-xs text-slate-500">
          Se tiver interesse em colaborar, contacte-nos através da página de
          <a href="/contacto" class="underline hover:text-slate-900">
            contacto
          </a>
          .
        </p>
      </section>
    </div>
  </UiContainer>
</template>

