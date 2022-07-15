<script setup lang="ts">
import { ref } from "vue";

const mobile_menu = ref(null);

function openNav(){
    mobile_menu.value.style.right = "0";
}

function closeNav(){
    mobile_menu.value.style.right = "-80%";
}

</script>

<template>
  <header>
    <nav class="nav-container">
        <router-link to="/">
            <img src="/src/assets/shared/desktop/logo.svg" class="nav-logo" alt="">
        </router-link>
        <div class="desktop-nav">
            <router-link to="/pricing" class="nav-element"><b>Pricing</b></router-link>
            <router-link to="/about" class="nav-element"><b>About</b></router-link>
            <router-link to="/contact" class="nav-element"><b>Contact</b></router-link>
            <button class="btn-primary nav-button"><b>Schedule a Demo</b></button>
        </div>
        <div class="mobile-nav">
            <img src="/src/assets/shared/mobile/menu.svg" @click="openNav()" class="hamburger-btn" alt="">
            <div ref="mobile_menu" class="mobile-menu">
                <div class="mobile-menu-nav">
                    <img src="/src/assets/shared/mobile/close.svg" @click="closeNav()" class="close-btn" alt="">
                    <div class="divider"></div>
                    <router-link to="/pricing" class="nav-element nav-element-mobile"><b>Pricing</b></router-link>
                    <router-link to="/about" class="nav-element nav-element-mobile"><b>About</b></router-link>
                    <router-link to="/contact" class="nav-element nav-element-mobile"><b>Contact</b></router-link>
                    <button class="btn-primary btn-nav-mobile"><b>Schedule a Demo</b></button>
                </div>
            </div>
        </div>
    </nav>
  </header>
  <router-view></router-view>
</template>

<style scoped>
</style>