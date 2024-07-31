<script setup lang="ts">
import { NLayout, NLayoutContent, NMessageProvider } from "naive-ui";
import TestView from "./components/TestView.vue";

</script>

<template>
  <n-message-provider>
    <n-layout>
      <n-layout-content>
        <test-view></test-view>
      </n-layout-content>
    </n-layout>
  </n-message-provider>
</template>

<style scoped></style>
