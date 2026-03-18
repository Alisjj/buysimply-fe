<script setup lang="ts">
import { computed, ref } from 'vue'
import { RouterLink } from 'vue-router'

const email = ref('')
const password = ref('')
const rememberMe = ref(false)
const passwordVisible = ref(false)

const passwordFieldType = computed(() =>
  passwordVisible.value ? 'text' : 'password',
)

const togglePasswordVisibility = () => {
  passwordVisible.value = !passwordVisible.value
}

const handleSubmit = () => {
  console.log('Login form submitted', {
    email: email.value,
    password: password.value,
    rememberMe: rememberMe.value,
  })
}
</script>

<template>
  <main
    class="min-h-screen bg-[radial-gradient(circle_at_top_left,#f4e9fb_0,#ffffff_38%),linear-gradient(180deg,#fffdfd_0%,#fcfbff_100%)]"
  >
    <section
      class="min-h-screen bg-white shadow-none min-[921px]:grid min-[921px]:grid-cols-[minmax(360px,1.02fr)_minmax(420px,1fr)] min-[921px]:shadow-[0_28px_60px_rgba(105,67,140,0.12)]"
    >
      <aside
        class="hidden content-start gap-[26px] rounded-r-[36px] bg-[#F8EAFF] px-[42px] pb-[44px] pt-6 min-[921px]:grid min-[921px]:[grid-template-rows:auto_auto_auto]"
      >
        <div class="justify-self-start">
          <img
            class="block w-[198px] max-w-full"
            src="/brand-mark.svg"
            alt="Team Achieve logo"
          />
        </div>

        <div
          class="mt-3 ml-3 w-[calc(100%-12px)] justify-self-start overflow-hidden rounded-[26px] bg-[linear-gradient(145deg,#f4f0f8_0%,#ddd0eb_100%)] shadow-[inset_0_0_0_1px_rgba(149,128,168,0.08)]"
        >
          <img
            class="block aspect-[1.52/1] w-full object-cover"
            src="/image.png"
            alt="Team Achieve campaign visual"
          />
        </div>

        <div class="mt-[6px] grid justify-items-center gap-[10px] text-center">
          <h2
            class="m-0 font-lora text-[20px] leading-[1.2] font-bold text-[#6f2c91]"
          >
            Team Achieve
          </h2>
          <p
            class="m-0 whitespace-nowrap font-lora text-[18px] leading-[1.35] font-bold text-[#68636f]"
          >
            Your perfect solution for funding your desires
          </p>
        </div>
      </aside>

      <section
        class="flex min-h-screen flex-col justify-center bg-white px-[58px] py-14 max-[920px]:justify-start max-[920px]:px-[18px] max-[920px]:pb-9 max-[920px]:pt-[42px]"
      >
        <div class="mb-[34px] flex justify-center min-[921px]:hidden">
          <img
            class="block w-40 max-w-full"
            src="/brand-mark.svg"
            alt="Team Achieve logo"
          />
        </div>

        <div
          class="mb-[34px] grid gap-[14px] text-center max-[920px]:mb-7 max-[920px]:gap-2.5"
        >
          <h1
            class="m-0 font-lora text-[clamp(2.7rem,2.5vw,3.7rem)] leading-[1.1] font-bold tracking-[-0.04em] text-[#6f2c91] max-[920px]:text-[2.15rem]"
          >
            Welcome Back
          </h1>
          <p
            class="m-0 font-noto text-base leading-[1.55] text-[#6a6770] max-[920px]:mx-auto max-[920px]:max-w-[320px] max-[920px]:text-[0.95rem]"
          >
            Enter your email address and password to access your account.
          </p>
        </div>

        <form
          class="grid gap-[22px] max-[920px]:gap-[18px]"
          @submit.prevent="handleSubmit"
        >
          <label class="grid gap-2.5">
            <span class="font-noto text-[0.95rem] leading-[1.25] text-[#4e4b52]">
              Email Address <span class="text-[#ed4d56]">*</span>
            </span>
            <input
              v-model="email"
              class="h-[50px] w-full rounded-[9px] border border-[#d9d0dd] bg-white px-4 font-noto text-[#4e4b52] outline-none transition-[border-color,box-shadow] duration-200 placeholder:font-noto placeholder:text-[#a1a1a8] focus:border-[#9051b2] focus:shadow-[0_0_0_3px_rgba(111,44,145,0.12)]"
              type="email"
              placeholder="Enter your email"
              autocomplete="email"
            />
          </label>

          <label class="grid gap-2.5">
            <span class="font-noto text-[0.95rem] leading-[1.25] text-[#4e4b52]">
              Password <span class="text-[#ed4d56]">*</span>
            </span>

            <div class="relative flex items-center">
              <input
                v-model="password"
                class="h-[50px] w-full rounded-[9px] border border-[#d9d0dd] bg-white px-4 pr-16 font-noto text-[#4e4b52] outline-none transition-[border-color,box-shadow] duration-200 placeholder:font-noto placeholder:text-[#a1a1a8] focus:border-[#9051b2] focus:shadow-[0_0_0_3px_rgba(111,44,145,0.12)]"
                :type="passwordFieldType"
                placeholder="Enter your password"
                autocomplete="current-password"
              />
              <button
                class="absolute right-0 top-0 grid h-[50px] w-14 place-items-center rounded-r-[9px] border border-[#d9d0dd] border-l-[#d1c5d9] bg-transparent text-[#8b8991]"
                type="button"
                :aria-label="
                  passwordVisible ? 'Hide password' : 'Show password'
                "
                @click="togglePasswordVisibility"
              >
                <svg
                  class="h-6 w-6"
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M2 12C4.8 7.6 8.02 5.4 12 5.4C15.98 5.4 19.2 7.6 22 12C19.2 16.4 15.98 18.6 12 18.6C8.02 18.6 4.8 16.4 2 12Z"
                    stroke="currentColor"
                    stroke-width="1.8"
                    stroke-linejoin="round"
                  />
                  <circle
                    cx="12"
                    cy="12"
                    r="3.2"
                    stroke="currentColor"
                    stroke-width="1.8"
                  />
                </svg>
              </button>
            </div>
          </label>

          <div class="mt-[-2px] flex items-center justify-between gap-4">
            <label
              class="inline-flex items-center gap-[10px] font-noto text-[0.92rem] text-[#8a8790]"
            >
              <span
                class="relative grid h-[21px] w-[21px] place-items-center rounded-[2px] border-2 border-[#8f8c93] bg-white"
              >
                <input
                  v-model="rememberMe"
                  type="checkbox"
                  class="absolute inset-0 m-0 cursor-pointer appearance-none opacity-0"
                />
                <svg
                  class="pointer-events-none h-[10px] w-[10px] text-[#61227D] transition-transform duration-150 ease-in-out"
                  :class="rememberMe ? 'scale-100' : 'scale-0'"
                  viewBox="0 0 12 12"
                  fill="currentColor"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M4.78 9.03L1.53 5.78L0.47 6.84L4.78 11.15L11.53 4.4L10.47 3.34L4.78 9.03Z"
                  />
                </svg>
              </span>
              <span>Remember me</span>
            </label>

            <RouterLink class="font-noto text-[0.94rem] text-[#6f2c91]" to="/login">
              Forgot Password?
            </RouterLink>
          </div>

          <button
            class="h-[49px] w-full cursor-pointer rounded-[9px] bg-[#61227D] font-noto text-base font-bold text-white transition-[background,transform] duration-200 hover:bg-[#521c6a] active:translate-y-px"
            type="submit"
          >
            Sign in
          </button>

          <p class="mt-[-8px] text-center font-noto text-[0.97rem] text-[#6a6770]">
            Don’t have an account?
            <RouterLink class="font-bold text-[#6f2c91]" to="/login">
              Sign up
            </RouterLink>
          </p>
        </form>
      </section>
    </section>
  </main>
</template>
