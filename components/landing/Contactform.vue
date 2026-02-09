<script setup>
import { onMounted } from "vue";

useHead({
  script: [
    {
      src: "https://web3forms.com/client/script.js",
      async: true,
      defer: true,
    },
  ],
});

onMounted(() => {
  const form = document.getElementById("form");
  const result = document.getElementById("result");

  if (!form || !result) return;

  if (form.dataset.listenerAttached === "true") return;
  form.dataset.listenerAttached = "true";

  form.addEventListener("submit", function (e) {
    e.preventDefault();

    form.classList.add("was-validated");
    if (!form.checkValidity()) {
      const firstInvalid = form.querySelector(":invalid");
      if (firstInvalid) firstInvalid.focus();
      return;
    }

    const formData = new FormData(form);
    const object = Object.fromEntries(formData);
    const json = JSON.stringify(object);

    result.style.display = "block";
    result.classList.remove("text-green-500", "text-red-500");
    result.innerHTML = "A enviar...";

    fetch("https://api.web3forms.com/submit", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Accept: "application/json",
      },
      body: json,
    })
      .then(async (response) => {
        const data = await response.json();

        if (response.status === 200) {
          result.classList.add("text-green-500");
          result.innerHTML = "Mensagem enviada com sucesso. Obrigado!";
        } else {
          console.log(response);
          result.classList.add("text-red-500");
          result.innerHTML =
            data?.message || "Não foi possível enviar. Tente novamente.";
        }
      })
      .catch((error) => {
        console.log(error);
        result.classList.add("text-red-500");
        result.innerHTML = "Ocorreu um erro. Tente novamente mais tarde.";
      })
      .then(() => {
        form.reset();
        form.classList.remove("was-validated");
        setTimeout(() => {
          result.style.display = "none";
        }, 5000);
      });
  });
});
</script>

<template>
  <form
    id="form"
    action="https://api.web3forms.com/submit"
    method="POST"
    class="needs-validation"
    novalidate
    aria-label="Formulário de contacto"
  >
    <input
      type="hidden"
      name="access_key"
      value="27e86841-627a-405c-987b-35e79aa887a3"
    />

    <input
      type="hidden"
      name="subject"
      value="Nova mensagem do site da Paróquia"
    />
    <input
      type="hidden"
      name="from_name"
      value="Site — Paróquia de Castelões de Recesinhos"
    />

    <input
      type="checkbox"
      class="hidden"
      style="display: none"
      name="botcheck"
    />

    <div class="mb-5">
      <label for="nome" class="sr-only">Nome</label>
      <input
        id="nome"
        type="text"
        name="name"
        placeholder="Nome completo"
        required
        autocomplete="name"
        class="w-full px-4 py-3 border-2 placeholder:text-gray-600 rounded-md outline-none focus:ring-4 border-gray-300 focus:border-gray-600 ring-gray-100"
      />
      <div class="empty-feedback invalid-feedback text-red-400 text-sm mt-1">
        Por favor, indique o seu nome completo.
      </div>
    </div>

    <div class="mb-5">
      <label for="email" class="sr-only">Endereço de email</label>
      <input
        id="email"
        type="email"
        name="email"
        placeholder="Endereço de email"
        required
        autocomplete="email"
        class="w-full px-4 py-3 border-2 placeholder:text-gray-600 rounded-md outline-none focus:ring-4 border-gray-300 focus:border-gray-600 ring-gray-100"
      />
      <div class="empty-feedback text-red-400 text-sm mt-1">
        Por favor, indique o seu endereço de email.
      </div>
      <div class="invalid-feedback text-red-400 text-sm mt-1">
        Por favor, indique um email válido.
      </div>
    </div>

    <div class="mb-3">
      <label for="mensagem" class="sr-only">Mensagem</label>
      <textarea
        id="mensagem"
        name="message"
        required
        placeholder="A sua mensagem"
        class="w-full px-4 py-3 border-2 placeholder:text-gray-600 rounded-md outline-none h-36 focus:ring-4 border-gray-300 focus:border-gray-600 ring-gray-100"
      ></textarea>
      <div class="empty-feedback invalid-feedback text-red-400 text-sm mt-1">
        Por favor, escreva a sua mensagem.
      </div>
    </div>

    <!-- hCaptcha (Web3Forms) -->
    <div class="h-captcha my-4" data-captcha="true" data-lang="pt"></div>

    <UiButton type="submit" size="lg" block>Enviar mensagem</UiButton>

    <div
      id="result"
      class="mt-3 text-center"
      role="status"
      aria-live="polite"
    ></div>
  </form>
</template>

<style>
.invalid-feedback,
.empty-feedback {
  display: none;
}

.was-validated :placeholder-shown:invalid ~ .empty-feedback {
  display: block;
}

.was-validated :not(:placeholder-shown):invalid ~ .invalid-feedback {
  display: block;
}

.is-invalid,
.was-validated :invalid {
  border-color: #dc3545;
}
</style>
