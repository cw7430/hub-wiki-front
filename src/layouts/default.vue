<script setup lang="ts">
import style from "./default.module.scss";
import DefaultHeader from "@/widgets/DefaultHeader.vue";
import DefaultFooter from "@/widgets/DefaultFooter.vue";
</script>

<template>
  <div>
    <DefaultHeader />
    <div :class="style.container">
      <main :class="style.body">
        <slot />
      </main>
      <DefaultFooter />
    </div>
  </div>
</template>
