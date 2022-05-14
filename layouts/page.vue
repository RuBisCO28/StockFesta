<script lang="ts" setup>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
</script>

<template>
  <div class="flex flex-col min-h-screen">
    <slot name="header">
      <Header />
    </slot>
    <slot />
    <slot name="footer">
      <Footer />
    </slot>
  </div>
</template>
