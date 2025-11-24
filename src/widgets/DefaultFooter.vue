<script setup lang="ts">
import style from "./DefaultFooter.module.scss";
</script>

<template>
  <footer :class="style.container">
    <div>© 2025 Hub Wiki. All rights reserved.</div>
    <div :class="style.space"></div>
    <div>
      허브위키는 백과사전이 아니며 검증되지 않았거나, 편향적이거나, 잘못된 서술이 있을 수 있습니다.
    </div>
  </footer>
</template>
