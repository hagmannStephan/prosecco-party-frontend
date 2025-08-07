<script setup lang="ts">
import LanguageSwitcher from '@/components/LanguageSwitcher.vue';
import GameSelector from '@/components/GameSelector.vue';
</script>
<template>
  <h1>Prosecco Party</h1>
  <LanguageSwitcher />
  <GameSelector class="game-elemts"
    imagePath="images/schnapsidee.png"
    gamePath="/schnapsidee/game-config"
    gameName="Schnapsidee"
    i18nKey="home.schnapsidee-redirect" />
</template>
<style lang="scss">
.game-elemts {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>