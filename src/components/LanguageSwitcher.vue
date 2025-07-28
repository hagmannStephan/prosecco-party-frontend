<script setup lang="ts">
import { computed } from 'vue'
import { useI18n } from 'vue-i18n'
import { useLanguageSettingsStore } from '@/stores/languageSettingsStore'

const { locale } = useI18n()
const languageSettingsStore = useLanguageSettingsStore()

const currentLocale = computed(() => locale.value)

function toggleLanguage() {
  const newLocale = locale.value === 'de' ? 'en' : 'de'
  locale.value = newLocale
  languageSettingsStore.setLanguage(newLocale)
}
</script>

<template>
  <div class="toggle" :class="{ right: currentLocale === 'en' }" @click="toggleLanguage">
    <div class="highlight"></div>
    <div class="option"><span>Deutsch</span></div>
    <div class="option"><span>English</span></div>
  </div>
</template>

<style lang="scss">
span {
  font-family: 'Oswald';
  font-weight: 400;
}

select {
  height: 2rem;
  background-color: #ecdcb3;
  color: #5A3866;
  border: 1px solid #5A3866;
  border-radius: 0.5rem;
  padding: 0 0.5rem;
  font-family: 'Inter', sans-serif;
  font-size: 1rem;
  outline: none;
  background-repeat: no-repeat;
  background-position: right 0.5rem center;
  background-size: 0.65rem;
  transition: border-color 0.2s ease-in-out, background-color 0.2s ease-in-out;
}

select:focus {
  border-color: #382240;
  background-color: #f6e8c9;
}

.toggle {
  background: #3d2358;
  border-radius: 100px;
  padding: 6px;
  display: flex;
  width: 180px;
  position: relative;
  justify-content: space-between;
  color: #fef1cc;
  font-size: 1rem;
  cursor: pointer;
}

.option {
  flex: 1;
  text-align: center;
  z-index: 2;
}

.highlight {
  position: absolute;
  background: #7e5d8d;
  border-radius: 100px;
  top: 6px;
  bottom: 6px;
  left: 6px;
  width: calc(50% - 6px);
  transition: left 0.3s;
  z-index: 1;
}

.right .highlight {
  left: 50%;
}
</style>