<template>
<!--    <header class="mw-100">-->
<!--        <Navbar />-->
<!--    </header>-->

        <RouterView />
</template>

<script setup lang="ts">
import Navbar from "@/components/NavbarMenu.vue";

</script>

<style lang="scss">
header {
  background-color: #fff;
  box-shadow: 0 6px 4px -4px rgba(0, 0, 0, 0.2);
}


</style>
