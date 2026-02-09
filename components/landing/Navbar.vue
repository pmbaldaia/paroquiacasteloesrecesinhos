<script setup>
const menuitems = [
  { title: "Início", path: "/" },
  { title: "Horários", path: "/horarios" },
  { title: "Notícias", path: "/noticias" },
  { title: "Sacramentos", path: "/sacramentos" },
];

const open = ref(false);
</script>
<template>
  <UiContainer>
    <header class="my-4 lg:my-6">
      <div class="flex items-center justify-between gap-3">
        <a href="/" class="flex min-w-0 items-center gap-3">
          <img
            src="/logo.png"
            alt="Paróquia de Castelões de Recesinhos"
            class="h-12 w-auto lg:h-20"
          />

          <span class="lg:hidden min-w-0">
            <span class="block truncate text-sm font-semibold text-gray-700">
              Paróquia de Castelões
            </span>
            <span class="block truncate text-xs text-gray-500">
              de Recesinhos
            </span>
          </span>
        </a>

        <nav class="hidden lg:block" aria-label="Menu principal">
          <ul class="flex items-center gap-2">
            <li v-for="item of menuitems" :key="item.title">
              <a
                :href="item.path"
                class="rounded-md px-3 py-2 text-gray-600 hover:text-gray-900 hover:bg-gray-50"
              >
                {{ item.title }}
              </a>
            </li>
          </ul>
        </nav>

        <div class="hidden lg:flex items-center gap-4">
          <a href="/contacto" class="text-gray-700 hover:text-gray-900"
            >Contacto</a
          >
          <UiLink href="/apoio" size="md">Apoiar</UiLink>
        </div>

        <button
          @click="open = !open"
          class="lg:hidden inline-flex items-center justify-center rounded-md p-3 text-gray-800 hover:bg-gray-100 active:bg-gray-200"
          :aria-expanded="open"
          aria-controls="mobile-menu"
          aria-label="Abrir menu principal"
        >
          <svg
            fill="currentColor"
            class="h-5 w-5"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              v-show="open"
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M18.278 16.864a1 1 0 01-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 01-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 011.414-1.414l4.829 4.828 4.828-4.828a1 1 0 111.414 1.414l-4.828 4.829 4.828 4.828z"
            />
            <path
              v-show="!open"
              fill-rule="evenodd"
              d="M4 5h16a1 1 0 010 2H4a1 1 0 110-2zm0 6h16a1 1 0 010 2H4a1 1 0 010-2zm0 6h16a1 1 0 010 2H4a1 1 0 010-2z"
            />
          </svg>
        </button>
      </div>

      <nav
        id="mobile-menu"
        class="lg:hidden mt-3"
        :class="open ? 'block' : 'hidden'"
        aria-label="Menu principal"
      >
        <div class="rounded-lg border border-gray-100 bg-white p-2 shadow-sm">
          <ul class="flex flex-col">
            <li v-for="item of menuitems" :key="item.title">
              <a
                :href="item.path"
                class="flex rounded-md px-3 py-2 text-gray-700 hover:bg-gray-50 hover:text-gray-900"
                @click="open = false"
              >
                {{ item.title }}
              </a>
            </li>
          </ul>

          <div class="mt-3 flex gap-3">
            <UiLink href="/contacto" styleName="muted" block size="md"
              >Contacto</UiLink
            >
            <UiLink href="/apoio" size="md" block>Apoiar</UiLink>
          </div>
        </div>
      </nav>
    </header>
  </UiContainer>
</template>
