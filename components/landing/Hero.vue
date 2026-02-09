<template>
  <main class="grid lg:grid-cols-2 place-items-center pt-4 pb-4 md:pt-8">
    <div class="p-6 md:p-24">
      <img
        class="w-full max-w-xs md:max-w-md rounded-lg object-contain transition-transform transform hover:scale-105 shadow-lg"
        src="~/assets/img/post.jpg"
        alt="Igreja de Castelões de Recesinhos"
        loading="eager"
        width="512"
        height="640"
      />
    </div>

    <div>
      <h1
        class="text-3xl sm:text-4xl lg:text-5xl xl:text-6xl font-bold lg:tracking-tight"
      >
        Bem-vindos à página da Paróquia de Castelões de Recesinhos!
      </h1>

      <p class="text-lg mt-4 text-slate-600 max-w-xl">
        Este é um espaço para estarmos mais próximos: partilhar a vida da nossa
        comunidade e acompanhar as obras de restauro e requalificação da Igreja,
        com atualizações do progresso, iniciativas e informação útil.
      </p>
      <p class="text-lg mt-4 text-slate-600 max-w-xl">
        Se quiser ajudar, colaborar ou colocar alguma questão, envie mensagem
        pela página.
      </p>
      <p class="text-lg mt-4 text-slate-600 max-w-xl font-medium">
        Obrigado por caminhar connosco.
      </p>
      <div class="mt-6 flex flex-col sm:flex-row gap-3">
        <UiLink href="/contact">Enviar mensagem</UiLink>
        <UiLink size="lg" styleName="outline" href="/about">Sobre nós</UiLink>
      </div>
    </div>
  </main>
</template>
