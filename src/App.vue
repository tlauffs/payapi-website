<script setup lang="ts">
import { ref } from "vue";

const mobile_menu = ref(null);

function openNav() {
  mobile_menu.value.style.right = "0";
}

function closeNav() {
  mobile_menu.value.style.right = "-80%";
}
</script>

<template>
  <header>
    <nav class="nav-container">
      <router-link to="/">
        <img
          src="/src/assets/shared/desktop/logo.svg"
          class="nav-logo"
          alt=""
        />
      </router-link>
      <div class="desktop-nav">
        <router-link to="/pricing" class="nav-element"
          ><b>Pricing</b></router-link
        >
        <router-link to="/about" class="nav-element"><b>About</b></router-link>
        <router-link to="/contact" class="nav-element"
          ><b>Contact</b></router-link
        >
        <button class="btn-primary nav-button"><b>Schedule a Demo</b></button>
      </div>
      <div class="mobile-nav">
        <img
          src="/src/assets/shared/mobile/menu.svg"
          @click="openNav()"
          class="hamburger-btn"
          alt=""
        />
        <div ref="mobile_menu" class="mobile-menu">
          <div class="mobile-menu-nav">
            <img
              src="/src/assets/shared/mobile/close.svg"
              @click="closeNav()"
              class="close-btn"
              alt=""
            />
            <div class="divider"></div>
            <router-link to="/pricing" class="nav-element"
              ><b>Pricing</b></router-link
            >
            <router-link to="/about" class="nav-element"
              ><b>About</b></router-link
            >
            <router-link to="/contact" class="nav-element"
              ><b>Contact</b></router-link
            >
            <button class="btn-primary btn-nav-mobile">
              <b>Schedule a Demo</b>
            </button>
          </div>
        </div>
      </div>
    </nav>
  </header>
  <router-view></router-view>
  <div class="footer">
    <div class="section flex-container pt-5">
      <div class="mb-3">
        <h2>Ready to start?</h2>
      </div>
      <div class="input-wrapper mb-3">
        <input class="input" placeholder="Enter email address " type="text" />
        <button class="btn-primary btn-demo">Schedule a Demo</button>
      </div>
    </div>
    <div class="flex-footer mt-3">
      <div class="nav-footer-ele">
        <router-link to="/">
        <img
          src="/src/assets/shared/desktop/logo.svg"
          class="nav-logo logo-white"
          alt=""
        />
        </router-link>
      </div>
      <router-link
        to="/pricing"
        class="nav-element-light white-text nav-footer-ele"
        ><b>Pricing</b></router-link
      >
      <router-link
        to="/about"
        class="nav-element-light white-text nav-footer-ele"
        ><b>About</b></router-link
      >
      <router-link
        to="/contact"
        class="nav-element-light white-text nav-footer-ele"
        ><b>Contact</b></router-link
      >
      <div class="socials nav-footer-ele">
        <img src="/src/assets/shared/desktop/facebook.svg" alt="" class="mlr social-btn" />
        <img src="/src/assets/shared/desktop/twitter.svg" alt="" class="mlr social-btn" />
        <img src="/src/assets/shared/desktop/linkedin.svg" alt="" class="mlr social-btn" />
      </div>
    </div>
  </div>
</template>

<style scoped>
/* footer styles*/
.flex-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}
.flex-footer {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  padding: 2rem clamp(0rem, 10.375rem, 7vw) 1.2rem clamp(0rem, 10.375rem, 7vw);
  background-color: var(--dark-blue);
}
.logo-white {
  filter: invert(100%) sepia(100%) saturate(0%) hue-rotate(288deg)
    brightness(102%) contrast(102%);
}
.nav-element:hover,
.nav-element:focus .nav-element:active {
  color: var(--light-blue);
}
.socials {
  margin-left: auto;
}

.social-btn{
    transition: all 250ms;
    cursor: pointer;
}

.social-btn:hover,
.social-btn:focus,
.social-btn:active  {
  opacity: 1;
  filter: invert(71%) sepia(15%) saturate(7094%) hue-rotate(297deg) brightness(72%) contrast(54%);
}
@media (max-width: 64rem) {
  .flex-container {
    justify-content: center;
  }
}
@media (max-width: 48rem) {
  .flex-footer {
    flex-direction: column;
  }
  .socials {
    margin-left: 0;
  }
  .nav-footer-ele {
    margin-bottom: 2rem;
  }
}
</style>