<script setup>
definePageMeta({
  layout: "landing",
});
</script>

<template>
  <UiContainer>
    <UiSectionhead>
      <template #title>Sobre a paróquia</template>
      <template #desc>
        Um espaço simples para apresentar a comunidade de Castelões de
        Recesinhos.
      </template>
    </UiSectionhead>

    <div class="flex flex-col gap-4 mx-auto max-w-4xl mt-16 text-slate-600">
      <p class="text-lg leading-relaxed">
        A Paróquia de Castelões de Recesinhos é uma comunidade viva, que se
        reúne à volta da Eucaristia, da Palavra de Deus e da vida fraterna. Ao
        longo do ano, muitas pessoas colaboram nas celebrações, catequese,
        grupos e iniciativas de solidariedade.
      </p>

      <p class="leading-relaxed">
        Este site nasce com o objetivo de aproximar ainda mais a comunidade,
        partilhando notícias, informações úteis, horários e o progresso das
        obras de restauro da Igreja paroquial.
      </p>

      <p class="leading-relaxed">
        Não pretende substituir o encontro presencial, mas ser um apoio para
        quem deseja acompanhar de perto a vida da paróquia, mesmo quando não
        pode estar fisicamente presente.
      </p>
    </div>
  </UiContainer>
</template>
