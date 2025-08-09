<script setup lang="ts">
const props = defineProps<{
    imagePath: string
    gamePath: string
    gameName: string
    i18nKey: string
}>()
</script>
<template>
    <div @click="$router.push(props.gamePath)"
         class="cursor-pointer">
        <img
            :src="props.imagePath"
            :alt="props.gameName"
            class="game-selector">
        <p class="game-name title">{{ $t(props.i18nKey) }}</p>
    </div>
</template>
<style lang="scss" scoped>
.game-selector {
    width: 80%;
    max-width: 280px;
    height: auto;
    display: block;
}
</style>
