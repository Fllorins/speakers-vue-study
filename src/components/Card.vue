<script setup>
defineProps({
  id: Number,
  imageUrl: String,
  title: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickAdd: Function,
  onClickFavorite: Function
})

// const visibleFavoriteButton = Boolean(props.onClickFavorite)
</script>
<template>
  <div
    class="relative bg-white border border-slate-100 rounded-3xl p-10 cursor-pointer transition duration hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      @click="onClickFavorite"
      class="absolute top-8 left-8"
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      alt="like"
    />
    <img :src="imageUrl" alt="sneakers" />
    <p class="mt-5">{{ title }}</p>

    <div class="flex justify-between mt-5">
      <div class="flex flex-col">
        <span class="text-slate-400">Цена:</span>
        <span>{{ price }} руб.</span>
      </div>

      <img
        @click="onClickAdd"
        :src="!isAdded ? '/plus.svg' : '/checked.svg'"
        alt="chek"
        class="cursor-pointer"
      />
    </div>
  </div>
</template>
