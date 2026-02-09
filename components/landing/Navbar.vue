<script setup>
const menuitems = [
  { title: "Início", path: "/" },
  { title: "Horários", path: "/horarios" },
  { title: "Notícias", path: "/noticias" },
  { title: "Contacto", path: "/contacto" },
];

const open = ref(false);
</script>
<template>
  <UiContainer>
    <header class="mt-3 mb-2 lg:mt-4 lg:mb-0">
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
          <a
            href="https://www.facebook.com/people/Igreja-de-Castel%C3%B5es/61587053586453/?locale=pt_PT"
            target="_blank"
            rel="noopener noreferrer"
            class="text-slate-300 hover:text-blue-600 transition-colors"
            aria-label="Página da paróquia no Facebook"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="32"
              height="32"
              fill="rgb(75 85 99)"
              viewBox="0 0 256 256"
            >
              <path
                d="M128,24A104,104,0,1,0,232,128,104.11,104.11,0,0,0,128,24Zm8,191.63V152h24a8,8,0,0,0,0-16H136V112a16,16,0,0,1,16-16h16a8,8,0,0,0,0-16H152a32,32,0,0,0-32,32v24H96a8,8,0,0,0,0,16h24v63.63a88,88,0,1,1,16,0Z"
              ></path>
            </svg>
          </a>
          <UiLink
            href="/apoio"
            size="md"
            styleName="outline"
            class="bg-white hover:bg-gray-100 text-gray-800 font-semibold py-2 px-4 border border-gray-400 rounded shadow"
          >
            Apoiar
          </UiLink>
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
        <div class="rounded-lg border border-gray-200 bg-white">
          <ul class="divide-y divide-gray-200">
            <li v-for="item of menuitems" :key="item.title">
              <a
                :href="item.path"
                class="block px-4 py-3 text-sm font-medium text-gray-700 hover:bg-gray-50 hover:text-gray-900"
                @click="open = false"
              >
                {{ item.title }}
              </a>
            </li>
          </ul>

          <div
            class="px-4 py-3 border-t border-gray-200 flex items-center justify-between"
          >
            <a
              href="https://www.facebook.com/people/Igreja-de-Castel%C3%B5es/61587053586453/?locale=pt_PT"
              target="_blank"
              rel="noopener noreferrer"
              class="text-sm text-gray-600 hover:text-blue-700"
              @click="open = false"
              aria-label="Página da paróquia no Facebook"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="32"
                height="32"
                fill="#000000"
                viewBox="0 0 256 256"
              >
                <path
                  d="M128,24A104,104,0,1,0,232,128,104.11,104.11,0,0,0,128,24Zm8,191.63V152h24a8,8,0,0,0,0-16H136V112a16,16,0,0,1,16-16h16a8,8,0,0,0,0-16H152a32,32,0,0,0-32,32v24H96a8,8,0,0,0,0,16h24v63.63a88,88,0,1,1,16,0Z"
                ></path>
              </svg>
            </a>

            <UiLink
              href="/apoio"
              size="md"
              styleName="outline"
              class="rounded-md border border-gray-300 bg-white px-3 py-2 text-sm font-semibold text-gray-800 hover:bg-gray-50"
              @click="open = false"
            >
              Apoiar
            </UiLink>
          </div>
        </div>
      </nav>
    </header>
  </UiContainer>
</template>
