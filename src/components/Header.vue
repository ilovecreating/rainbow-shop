<script setup>
const emit = defineEmits(['openDrawer'])

defineProps({
  totalPrice: Number
})
</script>

<template>
  <header class="ph600:flex ph600:justify-between border-b border-slate 200 px-10 py-8">
    <router-link to="/rainbow-shop/"
      ><div class="flex items-center gap-4">
        <img src="/logo.png" alt="Logo" class="w-10" />
        <div>
          <h2 class="text-xl font-bold uppercase">Vue Rainbows</h2>
          <p class="text-slate-400">Магазин топовых арбалетов</p>
        </div>
      </div></router-link
    >
    <ul class="grid grid-cols-1 gap-4 ph420:flex ph420:items-center ph420:gap-10">
      <li
        @click="() => emit('openDrawer')"
        class="flex items-center gap-3 text-gray-500 cursor-pointer hover:text-black"
      >
        <img src="/cart.svg" alt="Cart" />
        <b>{{ totalPrice }}</b>
      </li>

      <router-link to="/rainbow-shop/favorites"
        ><li class="flex items-center gap-3 text-gray-500 cursor-pointer hover:text-black">
          <img src="/heart.svg" alt="Cart" />
          <span>Закладки</span>
        </li></router-link
      >

      <li class="flex items-center gap-3 text-gray-500 cursor-pointer hover:text-black">
        <img src="/profile.svg" alt="Cart" />
        <span>Профиль</span>
      </li>
    </ul>
  </header>
</template>
