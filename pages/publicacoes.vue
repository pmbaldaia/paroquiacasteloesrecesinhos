<script setup>
definePageMeta({ layout: "landing" });

const posts = [
  {
    id: 1,
    title: "Foral de 1513",
    message:
      "Em 1513, D. Manuel I deu o Foral a Santa Cruz de Riba Tâmega e há um detalhe delicioso: a Igreja de Castelões pagava ao senhor da terra um imposto.\n\nIsto mostra que, já no séc. XVI, a paróquia tinha estrutura e bens reconhecidos.",
    // vídeo “horizontal”
    ratioClass: "aspect-video",
    iframe: `<iframe src="https://www.facebook.com/plugins/video.php?height=314&href=https%3A%2F%2Fwww.facebook.com%2Freel%2F1268570462084319%2F&show_text=false&width=560&t=0"
      style="border:none;overflow:hidden" scrolling="no" frameborder="0"
      allowfullscreen="true" allow="autoplay; clipboard-write; encrypted-media; picture-in-picture; web-share"></iframe>`,
  },
  {
    id: 2,
    title: "Publicação",
    message: "",
    // reel vertical
    ratioClass: "aspect-[9/16]",
    iframe: `<iframe src="https://www.facebook.com/plugins/video.php?height=476&href=https%3A%2F%2Fwww.facebook.com%2Freel%2F1583351839670995%2F&show_text=false&width=267&t=0"
      style="border:none;overflow:hidden" scrolling="no" frameborder="0"
      allowfullscreen="true" allow="autoplay; clipboard-write; encrypted-media; picture-in-picture; web-share"></iframe>`,
  },
  {
    id: 3,
    title: "A Igreja de Castelões precisa de nós",
    message:
      "A Igreja de Castelões precisa de nós!\nO tempo não perdoa e a urgência de agir é agora.\n\nEm apenas 3 passos podes fazer a diferença na preservação do nosso património.\nVê o vídeo e envia-nos uma mensagem para saberes como ajudar!",
    ratioClass: "aspect-[9/16]",
    iframe: `<iframe src="https://www.facebook.com/plugins/video.php?height=476&href=https%3A%2F%2Fwww.facebook.com%2Freel%2F1564813607937821%2F&show_text=false&width=267&t=0"
      style="border:none;overflow:hidden" scrolling="no" frameborder="0"
      allowfullscreen="true" allow="autoplay; clipboard-write; encrypted-media; picture-in-picture; web-share"></iframe>`,
  },
];
</script>

<template>
  <UiContainer>
    <UiSectionhead>
      <template #title>Publicações</template>
      <template #desc>
        Acompanhe as novidades, comunicados e iniciativas da paróquia associada à sua página de facebook.
      </template>
    </UiSectionhead>

    <div class="mt-10 mx-auto max-w-6xl">
      <!-- GRID optimizada -->
      <div class="grid grid-cols-1 gap-6 lg:grid-cols-2">
        <article
          v-for="post in posts"
          :key="post.id"
          class="group rounded-2xl border border-slate-200 bg-white shadow-sm transition hover:shadow-md"
        >
          <div class="p-5 sm:p-6">
            <h2 class="text-base sm:text-lg font-semibold text-slate-900">
              {{ post.title }}
            </h2>

            <p
              v-if="post.message"
              class="mt-3 text-sm sm:text-[15px] leading-relaxed text-slate-700 whitespace-pre-line"
            >
              {{ post.message }}
            </p>
          </div>

          <!-- VIDEO responsivo com Tailwind -->
          <div class="px-5 pb-5 sm:px-6 sm:pb-6">
            <div
              class="relative w-full overflow-hidden rounded-xl bg-slate-100"
              :class="post.ratioClass"
            >
              <div
                class="absolute inset-0 [&_iframe]:h-full [&_iframe]:w-full [&_iframe]:border-0"
                v-html="post.iframe"
              />
            </div>
          </div>
        </article>
      </div>

      <!-- Placeholder se não houver posts -->
      <div
        v-if="posts.length === 0"
        class="mt-12 max-w-3xl mx-auto text-slate-700"
      >
        <div class="rounded-2xl border border-dashed border-slate-300 bg-slate-50 px-6 py-10 text-center">
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
    </div>
  </UiContainer>
</template>
