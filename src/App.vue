<script setup lang="ts">
import { ref } from "vue";

const mobile_menu = ref("");
const email = ref("");
const emailError = ref(false);

function openNav() {
  mobile_menu.value.style.right = "0";
}

function closeNav() {
  mobile_menu.value.style.right = "-80%";
}

function onSubmitSchedule() {
  var isValid = true;
  emailError.value = false;
  if (!/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(email.value)) {
    emailError.value = true;
    isValid = false;
  }
  if (isValid) {
    alert(email.value);
  }
}

function scheduleClick() {
  window.scrollTo(0, document.body.scrollHeight);
}
</script>

<template>
  <div>
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
          <router-link to="/about" class="nav-element"
            ><b>About</b></router-link
          >
          <router-link to="/contact" class="nav-element"
            ><b>Contact</b></router-link
          >
          <button class="btn-primary nav-button" @click="scheduleClick()">
            <b>Schedule a Demo</b>
          </button>
        </div>
        <div class="mobile-nav">
          <img
            src="/src/assets/shared/mobile/menu.svg"
            @click="openNav()"
            class="hamburger-btn"
            alt=""
          />
        </div>
      </nav>
    </header>
    <router-view></router-view>
    <div class="footer">
      <div class="section flex-container pt-5">
        <div class="mb-3">
          <h2 class="flex-md-center">Ready to start?</h2>
        </div>
        <div class="mb-3">
          <form
            @submit.prevent
            @submit="onSubmitSchedule()"
            novalidate
            class="mt"
          >
            <div class="input-wrapper">
              <input
                :class="{ error: emailError }"
                class="input"
                v-model="email"
                placeholder="Enter email address"
                type="email"
              />
              <button type="submit" class="btn-primary btn-demo">
                Schedule a Demo
              </button>
            </div>
            <p v-if="emailError" class="form-error">
              Please enter a valid e-mail address
            </p>
          </form>
        </div>
      </div>
      <div class="flex-footer mt-3">
        <div class="overflow-wrapper">
          <div class="circle footer-circle"></div>
        </div>
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
          <img
            src="/src/assets/shared/desktop/facebook.svg"
            alt=""
            class="mlr social-btn"
          />
          <img
            src="/src/assets/shared/desktop/twitter.svg"
            alt=""
            class="mlr social-btn"
          />
          <img
            src="/src/assets/shared/desktop/linkedin.svg"
            alt=""
            class="mlr social-btn"
          />
        </div>
      </div>
    </div>
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
        <router-link to="/about" class="nav-element"><b>About</b></router-link>
        <router-link to="/contact" class="nav-element"
          ><b>Contact</b></router-link
        >
        <button class="btn-primary btn-nav-mobile">
          <b>Schedule a Demo</b>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* footer styles*/
.flex-container {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.flex-footer {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  overflow: hidden;
  padding: 2rem clamp(0rem, 10.375rem, 7vw) 1.2rem clamp(0rem, 10.375rem, 7vw);
  background-color: var(--dark-blue);
}
.logo-white {
  filter: invert(100%) sepia(100%) saturate(0%) hue-rotate(288deg)
    brightness(102%) contrast(102%);
}

.socials {
  margin-left: auto;
}

.social-btn {
  transition: all 250ms;
  cursor: pointer;
}

.social-btn:hover,
.social-btn:focus,
.social-btn:active {
  opacity: 1;
  filter: invert(71%) sepia(15%) saturate(7094%) hue-rotate(297deg)
    brightness(72%) contrast(54%);
}
@media (max-width: 64rem) {
  .flex-container {
    justify-content: center;
    flex-direction: column;
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