<script setup lang="ts">
const name = ref('')

const router = useRouter()
function go() {
  if (name.value)
    router.push(`/hi/${encodeURIComponent(name.value)}`)
}
</script>

<template>
  <div>
    <div class="text-4xl inline-block" i-carbon-campsite />
    <p>
      <a
        rel="noreferrer"
        href="https://github.com/Simon-He95/vitesse-lite"
        target="_blank"
        class="bg-amber-100"
      >
        Vitesse Lite
      </a>
    </p>
    <p>
      <em class="text-sm op75">Opinionated Vite Starter Template</em>
    </p>

    <div class="py-4" />

    <input
      id="input"
      v-model="name"
      class="border-dark:gay-700 active:outline-none outline-none border-gray-200 border-solid rounded bg-transparent text-center w-[250px] px-4 py-2"
      placeholder="What's your name?"
      type="text"
      autocomplete="false"
      @keydown.enter="go"
    >

    <div>
      <button class="m-3 text-sm btn" :disabled="!name" @click="go">
        Go
      </button>
    </div>
  </div>
</template>
