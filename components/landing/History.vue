<script setup>
const videoSrc =
  "https://www.facebook.com/plugins/video.php?height=314&href=https%3A%2F%2Fwww.facebook.com%2Freel%2F3293260624146022%2F&show_text=false&width=560&t=0";
</script>

<template>
  <section class="mt-12 sm:mt-12 lg:mt-4">
    <div class="max-w-3xl">
      <h2
        class="mt-2 text-3xl sm:text-4xl lg:text-5xl font-bold lg:tracking-tight"
      >
        Origens medievais da Igreja
      </h2>

      <p class="text-base sm:text-lg mt-4 text-slate-600">
        Neste primeiro momento da nossa viagem, olhamos para as origens
        medievais da Igreja de Castelões de Recesinhos, o seu surgimento e o
        papel que desempenhou na comunidade ao longo dos séculos.
      </p>
    </div>

    <div class="mt-12">
      <div
        class="relative w-full overflow-hidden rounded-xl shadow-lg bg-black/5 aspect-video"
      >
        <iframe
          class="absolute inset-0 h-full w-full"
          :src="videoSrc"
          style="border: none; overflow: hidden"
          scrolling="no"
          frameborder="0"
          allow="
            autoplay;
            clipboard-write;
            encrypted-media;
            picture-in-picture;
            web-share;
          "
          allowfullscreen
          title="Origens medievais da Igreja de Castelões de Recesinhos"
        ></iframe>
      </div>
    </div>
  </section>
</template>
