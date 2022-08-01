<script setup lang="ts">
import { ref } from "vue";

const email = ref("");
const emailError = ref(false);

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
</script>
<template>
  <div>
    <div class="overflow-wrapper top-wrapper">
      <div class="circle top-circle"></div>
    </div>
    <div class="grid-container section">
      <div class="grid-item header-text">
        <h1>Start building with our APIs for absolutely free.</h1>
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
        <p class="indent">
          Have any questions?
          <router-link to="/contact" class="btn-link"
            ><b>Contact Us</b></router-link
          >
        </p>
      </div>
      <div class="grid-item phone-item">
        <img
          src="/src/assets/home/desktop/illustration-phone-mockup.svg"
          class="phone-img"
          alt=""
        />
      </div>
    </div>
    <div class="overflow-wrapper">
      <div class="circle dark-circle"></div>
    </div>
    <div class="dark-section">
      <div class="grid-container">
        <div class="max-text-width">
          <h2 class="white-text">Who we work with</h2>

          <p class="white-text opaque">
            Today, millions of people around the world have successfully
            connected their accounts to apps they love using our API. We provide
            developers with the tools they need to create easy and accessible
            experiences for their users.
          </p>
          <div class="mt-3 mb">
            <router-link to="/about" class="btn-sec-light"
              >About Us</router-link
            >
          </div>
        </div>
        <div class="logo-grid-wrapper">
          <div class="logo-grid">
            <div><img src="/src/assets/shared/desktop/tesla.svg" alt="" /></div>
            <div>
              <img src="/src/assets/shared/desktop/microsoft.svg" alt="" />
            </div>
            <div>
              <img
                src="/src/assets/shared/desktop/hewlett-packard.svg"
                alt=""
              />
            </div>
            <div>
              <img src="/src/assets/shared/desktop/oracle.svg" alt="" />
            </div>
            <div>
              <img src="/src/assets/shared/desktop/google.svg" alt="" />
            </div>
            <div>
              <img src="/src/assets/shared/desktop/nvidia.svg" alt="" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="grid-container section pt-5">
      <div>
        <img
          src="/src/assets/home/desktop/illustration-easy-to-implement-cropped.svg"
          class="implement-img"
          alt=""
        />
      </div>
      <div class="grid-item">
        <div class="implement-text">
          <h2>Easy to implement</h2>
          <p>
            Our API comes with just a few lines of code. You’ll be up and
            running in no time. We built our documentation page to integrate
            payments functionality with ease.
          </p>
        </div>
      </div>
    </div>
    <div class="overflow-wrapper">
      <div class="circle right-circle"></div>
    </div>
    <div class="grid-container section pt-5">
      <div class="grid-item">
        <div class="implement-text mr-2">
          <h2>Simple UI & UX</h2>
          <p>
            Our pre-built form is easy to integrate in your app or website’s
            checkout flow and designed to optimize conversion.
          </p>
        </div>
      </div>
      <div class="phone-item">
        <img
          src="/src/assets/home/desktop/illustration-simple-ui.svg"
          class="ui-img"
          alt=""
        />
      </div>
    </div>
    <div class="grid-container-3-col section pt-5">
      <div>
        <img src="/src/assets/home/desktop/icon-personal-finances.svg" alt=""/>
        <p class="p-header">Personal Finances</p>
        <p>
          Consolidate financial data from multiple sources and categorize
          transactions up to 2 years of history. Analyze reports to reconcile
          activities in your account.
        </p>
      </div>
      <div>
        <img src="/src/assets/home/desktop/icon-banking-and-coverage.svg" alt=""/>
        <p class="p-header">Banking & Coverage</p>
        <p>
          With our platform, you can speed up account onboarding and support
          ongoing payments for checking, savings, credit card, and brokerage
          accounts.
        </p>
      </div>
      <div>
        <img src="/src/assets/home/desktop/icon-consumer-payments.svg" alt=""/>
        <p class="p-header">Consumer Payments</p>
        <p>
          It’s easier to set up secure bank payments with us through a flow
          designed with the user experience in mind. Customers could instantly
          authenticate their account.
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* layout styles */

.grid-container {
  display: grid;
  align-items: center;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 1fr;
  gap: 1rem;
}
.grid-item {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.phone-img {
  margin-left: clamp(0px, 15%, 120px);
  max-width: clamp(0rem, 25rem, 100%);
}
.header-text {
  margin-bottom: 5rem;
}
.demo-input {
  margin-top: 2rem;
}
.max-text-width {
  max-width: 28rem;
}
.implement-text {
  max-width: 38rem;
}
.implement-img {
  width: min(80vw, 28rem);
  margin-right: 1rem;
}
.ui-img {
  width: min(80vw, 42rem);
  margin-right: 1rem;
}
.grid-container-3-col {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 7%;
  text-align: center;
}

/* responsiveness query */
@media (max-width: 48rem) {
  .grid-container-3-col {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
}
@media (max-width: 64rem) {
  .grid-container {
    grid-template-columns: 1fr;
    grid-template-rows: 2;
    justify-items: center;
    text-align: center;
  }
  .phone-img {
    margin: 0 auto;
    padding-left: 8%;
    max-width: clamp(0rem, 25rem, 100%);
  }
  .implement-text {
    margin: 0 auto;
  }
  .implement-img {
    margin-right: 0;
    margin-bottom: 3rem;
  }
  .phone-item {
    grid-row: 1;
  }
  .demo-input {
    margin-left: auto;
    margin-right: auto;
  }
  .logo-grid-wrapper {
    grid-row: 1;
    margin-bottom: 4rem;
  }
}
</style>
