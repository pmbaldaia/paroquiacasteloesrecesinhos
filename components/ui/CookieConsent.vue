<script setup lang="ts">
const visible = ref(false);

const STORAGE_KEY = "paroquia_cookie_consent_v1";

onMounted(() => {
  const stored = localStorage.getItem(STORAGE_KEY);
  if (!stored) {
    visible.value = true;
  }
});

function setConsent(value: string) {
  localStorage.setItem(STORAGE_KEY, value);
  visible.value = false;
}

function accept() {
  setConsent("accepted");
}

function close() {
  // Apenas fecha sem registar aceitação explícita
  setConsent("closed");
}
</script>

<template>
  <Teleport to="body">
    <transition name="fade">
      <div
        v-if="visible"
        class="fixed inset-0 z-40 flex items-end justify-center sm:items-center bg-black/40"
      >
        <div
          class="relative z-50 w-full max-w-lg rounded-2xl bg-white px-5 py-4 shadow-xl mx-3 mb-4 sm:mx-0 sm:mb-0"
          role="dialog"
          aria-modal="true"
          aria-labelledby="cookie-consent-title"
        >
          <button
            type="button"
            class="absolute right-3 top-3 text-slate-400 hover:text-slate-600"
            aria-label="Fechar aviso de cookies"
            @click="close"
          >
            <Icon name="uil:times" class="w-4 h-4" />
          </button>

          <h2
            id="cookie-consent-title"
            class="text-sm font-semibold text-slate-900 pr-6"
          >
            Utilização de cookies
          </h2>
          <p class="mt-2 text-xs text-slate-600">
            Este site utiliza cookies simples para garantir o seu
            funcionamento básico e, se necessário, para fins estatísticos.
            Ao continuar a navegar, pode aceitar a utilização de cookies.
            Pode saber mais na
            <NuxtLink
              to="/politica-cookies"
              class="underline hover:text-slate-900"
            >
              Política de Cookies.
            </NuxtLink>
          </p>

          <div class="mt-4 flex flex-col sm:flex-row gap-2 justify-end">
            <button
              type="button"
              class="inline-flex items-center justify-center rounded-md border border-slate-200 px-3 py-1.5 text-xs font-medium text-slate-600 hover:bg-slate-50"
              @click="close"
            >
              Fechar
            </button>
            <button
              type="button"
              class="inline-flex items-center justify-center rounded-md bg-slate-900 px-4 py-1.5 text-xs font-semibold text-white hover:bg-slate-800"
              @click="accept"
            >
              Concordo
            </button>
          </div>
        </div>
      </div>
    </transition>
  </Teleport>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

