<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <main
    class="flex min-h-screen items-center justify-center bg-[radial-gradient(circle_at_top_left,#f4e9fb_0,#ffffff_38%),linear-gradient(180deg,#fffdfd_0%,#fcfbff_100%)] px-5 py-6"
  >
    <section
      class="rounded-[24px] border border-[#eadcf4] bg-white px-8 py-6 text-center shadow-[0_28px_60px_rgba(105,67,140,0.12)]"
    >
      <p class="m-0 font-noto text-base text-[#6a6770]">
        Go to
        <RouterLink class="font-semibold text-[#6f2c91] underline" to="/login">
          login
        </RouterLink>
      </p>
    </section>
  </main>
</template>
