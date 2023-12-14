<script setup lang="ts">
const drawing = ref(false);

const navToggle = () => {
  drawing.value = !drawing.value
}

const items = ["a", "i", "u"]
</script>

<template>
  <v-app>
    <v-app-bar color="primary">
      <v-app-bar-nav-icon variant="text" @click="navToggle">
      </v-app-bar-nav-icon>
      <v-app-bar-title>
        Nuxt3 Vutify3 Applications
      </v-app-bar-title>
    </v-app-bar>
    <v-navigation-drawer v-model="drawing">
      <v-list>
        <v-list-subheader>LIST</v-list-subheader>
        <v-list-item v-for="(item, i) in items" :key="i" :value="item" color="primary" rounded="xl">
          {{ item }}
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-container>
        <slot />
      </v-container>
    </v-main>
  </v-app>
</template>