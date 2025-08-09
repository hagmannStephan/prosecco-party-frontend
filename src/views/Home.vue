<script setup lang="ts">
import LanguageSwitcher from '@/components/LanguageSwitcher.vue';
import GameSelector from '@/components/GameSelector.vue';
</script>
<template>
  <h1>Prosecco Party</h1>
  <LanguageSwitcher />
  <GameSelector 
    class="flex flex-col items-center"
    imagePath="images/schnapsidee.png"
    gamePath="/schnapsidee/game-config"
    gameName="Schnapsidee"
    i18nKey="home.schnapsidee-redirect" />
</template>