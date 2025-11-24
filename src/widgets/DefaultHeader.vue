<script setup lang="ts">
import { ref } from "vue";
import { useRouter } from "vue-router";
import style from "./DefaultHeader.module.scss";

const text = ref("");
const router = useRouter();

const handleSubmit = () => {
  if (text.value.trim() === "") return;
  router.push(`/w/${text.value}`);
};
</script>

<template>
  <header>
    <div :class="style.mainHeader">
      <NuxtLink to="/">
        <div>허브위키</div>
      </NuxtLink>
    </div>
    <div>
      <form :class="style.searchBox" @submit.prevent="handleSubmit">
        <input :class="style.searchInput" type="text" placeholder="Search" v-model="text" />
      </form>
    </div>
  </header>
</template>
