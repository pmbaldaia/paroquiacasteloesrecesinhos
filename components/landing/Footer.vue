<template>
  <footer class="mt-16 mb-12 px-4">
    <hr class="my-8">
    <p
      class="text-center text-xs text-slate-500 max-w-2xl mx-auto leading-relaxed"
    >
      Página dedicada à vida da
      comunidade e às obras de restauro da Igreja, com partilha de iniciativas,
      progresso dos trabalhos e informação útil.
    </p>

    <div
      class="mt-4 flex flex-col items-center gap-2 text-[11px] text-slate-400"
    >
      <div class="flex flex-wrap justify-center gap-x-4 gap-y-1">
        <NuxtLink
          to="/politica-privacidade"
          class="hover:text-slate-600 hover:underline"
        >
          Política de Privacidade
        </NuxtLink>
        <span class="hidden sm:inline text-slate-300">·</span>
        <NuxtLink
          to="/politica-cookies"
          class="hover:text-slate-600 hover:underline"
        >
          Política de Cookies
        </NuxtLink>
        <span class="hidden sm:inline text-slate-300">·</span>
        <NuxtLink
          to="/termos-utilizacao"
          class="hover:text-slate-600 hover:underline"
        >
          Termos de Utilização
        </NuxtLink>
      </div>

      <p>
        © {{ new Date().getFullYear() }} Paróquia de Castelões de Recesinhos ·
        by
        <a
          href="https://webcreaterpt.pt"
          target="_blank"
          rel="noopener noreferrer"
          class="underline hover:text-slate-500"
        >
          Webcreaterpt
        </a>
      </p>
    </div>
  </footer>
</template>
