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
        Formas simples de apoiar o restauro da Igreja e a vida da comunidade.
      </template>
    </UiSectionhead>

    <div class="mt-10 grid gap-8 md:grid-cols-3 max-w-5xl mx-auto">
      <section
        class="rounded-2xl border border-slate-200 p-6 bg-white flex flex-col"
      >
        <h2 class="text-lg font-semibold text-gray-800">
          Donativo para o restauro
        </h2>

        <p class="mt-2 text-sm text-slate-600">
          Pode contribuir com um donativo pontual para apoiar diretamente as
          obras de restauro da Igreja.
        </p>

        <div class="mt-auto pt-5">
          <UiLink
            href="/contacto"
            styleName="outline"
            class="w-full text-center"
          >
            Pedir dados para donativo
          </UiLink>

          <p class="mt-3 text-xs text-slate-500">
            Os dados são partilhados através de contacto direto, para garantir
            clareza e segurança.
          </p>
        </div>
      </section>

      <section
        class="rounded-2xl border border-slate-200 p-6 bg-white flex flex-col"
      >
        <h2 class="text-lg font-semibold text-gray-800">Apoio regular</h2>

        <p class="mt-2 text-sm text-slate-600">
          Se preferir, pode apoiar de forma regular. Este gesto ajuda a manter o
          acompanhamento das obras e as necessidades da comunidade ao longo do
          ano.
        </p>

        <div class="mt-auto pt-5">
          <UiLink
            href="/contacto"
            styleName="outline"
            class="w-full text-center"
          >
            Falar connosco
          </UiLink>

          <p class="mt-3 text-xs text-slate-500">
            Partilhamos consigo as opções disponíveis para contribuição
            periódica.
          </p>
        </div>
      </section>

      <section
        class="rounded-2xl border border-slate-200 p-6 bg-white flex flex-col"
      >
        <h2 class="text-lg font-semibold text-gray-800">Voluntariado</h2>

        <p class="mt-2 text-sm text-slate-600">
          O seu tempo e disponibilidade também são uma forma de apoio. Há várias
          tarefas em que pode ajudar, conforme a sua disponibilidade.
        </p>

        <div class="mt-auto pt-5">
          <UiLink
            href="/contacto"
            styleName="outline"
            class="w-full text-center"
          >
            Quero colaborar
          </UiLink>

          <p class="mt-3 text-xs text-slate-500">
            Basta enviar uma mensagem e indicamos como pode participar.
          </p>
        </div>
      </section>
    </div>
  </UiContainer>
</template>
