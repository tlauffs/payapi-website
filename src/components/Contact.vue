<script setup lang="ts">
import { ref } from "vue";

const name = ref("");
const email = ref("");
const company = ref("");
const title = ref("");
const message = ref("");
const checkbox = ref(false);

const nameError = ref(false);
const emailError = ref(false);
const messageError = ref(false);

function onSubmitContact() {
  var isValid = true;
  nameError.value = false;
  emailError.value = false;
  messageError.value = false;

  if (name.value === "") {
    nameError.value = true;
    isValid = false;
  }
  if (!/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(email.value)) {
    emailError.value = true;
    isValid = false;
  }
  if (message.value === "") {
    messageError.value = true;
    isValid = false;
  }
  if (isValid) {
    alert(
      name.value +
        email.value +
        company.value +
        title.value +
        message.value +
        checkbox.value
    );
  }
}
</script>

<template>
  <div>
    <div class="overflow-wrapper top-wrapper">
      <div class="circle top-sec-circle"></div>
    </div>
    <div class="section mt">
      <div class="flex-md-center">
        <h2 class="header-contact h2-big">
          Submit a help request and we’ll get in touch shortly.
        </h2>
      </div>
      <div class="form-grid mt-3">
        <div class="md-center">
          <form @submit.prevent @submit="onSubmitContact()" novalidate>
            <div>
              <input
                :class="{ error: nameError }"
                type="text"
                class="text-input"
                v-model="name"
                placeholder="Name"
              />
              <p v-if="nameError" class="form-error">
                This field can't be empty
              </p>
            </div>
            <div>
              <input
                :class="{ error: emailError }"
                type="email"
                class="text-input"
                v-model="email"
                placeholder="Email Address"
              />
              <p v-if="emailError" class="form-error">
                Please enter a valid e-mail address
              </p>
            </div>
            <div>
              <input
                type="text"
                class="text-input"
                v-model="company"
                placeholder="Company Name (optional)"
              />
            </div>
            <div>
              <input
                type="text"
                v-model="title"
                class="text-input"
                placeholder="Title (optional)"
              />
            </div>
            <div>
              <textarea
                :class="{ error: messageError }"
                type="textarea"
                v-model="message"
                class="text-input"
                placeholder="Message"
              ></textarea>
              <p v-if="messageError" class="form-error">
                This field can't be empty
              </p>
            </div>
            <div>
              <div class="checkbox">
                <input
                  type="checkbox"
                  class="checkbox-check"
                  v-model="checkbox"
                  id="subscribeAPI"
                  name="subscribeAPI"
                />
                <p class="checkbox-label" for="subscribeAPI">
                  Stay up-to-date with company announcements and updates to our
                  API
                </p>
              </div>
            </div>
            <button class="btn-sec mt-2" type="submit"><b>Submit</b></button>
          </form>
        </div>
        <div class="grid-right">
          <h4 class="flex-md-center">
            Join the thousands of innovators already building with us
          </h4>
          <div class="logo-grid-wrapper mt-3">
            <div class="logo-grid">
              <div>
                <img src="/src/assets/shared/desktop/tesla_blue.svg" alt="" />
              </div>
              <div>
                <img
                  src="/src/assets/shared/desktop/microsoft_blue.svg"
                  alt=""
                />
              </div>
              <div>
                <img
                  src="/src/assets/shared/desktop/hewlett-packard_blue.svg"
                  alt=""
                />
              </div>
              <div>
                <img src="/src/assets/shared/desktop/oracle_blue.svg" alt="" />
              </div>
              <div>
                <img src="/src/assets/shared/desktop/google_blue.svg" alt="" />
              </div>
              <div>
                <img src="/src/assets/shared/desktop/nvidia_blue.svg" alt="" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.header-contact {
  width: clamp(0rem, 100%, 42rem);
}

.form-grid {
  display: grid;
  align-items: center;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 1fr;
  gap: 3rem;
}

.grid-right {
    margin-bottom: 5rem;
}

@media (max-width: 64rem) {
  .form-grid {
    grid-template-columns: 1fr;
    grid-template-rows: repeat(2, auto);
  }
  .grid-right {
    margin: 3rem 0;
  }
}

.text-input {
  width: clamp(0rem, 100%, 34rem);
  background-color: transparent;
  border: none;
  border-bottom: 1px solid var(--light-blue);
  padding: 1rem 0rem; 
  opacity: 1;
  margin-top: 1rem;
}

::placeholder {
  font-weight: 400;
}

:-ms-input-placeholder {
  font-weight: 400;
}

input:hover::placeholder,
input:focus::placeholder,
textarea:hover::placeholder,
textarea:hover::placeholder {
  color: var(--blue);
  opacity: 1;
}

textarea {
  height: 4rem;
}
.error::placeholder {
  color: var(--error);
}

.checkbox {
  width: clamp(0rem, 100%, 34rem);
  display: flex;
  align-items: center;
  margin-top: 1rem;
}
.checkbox-check {
  -webkit-appearance: none;
  width: 1.4rem;
  height: 1.4rem;
  flex-shrink: 0;
  background-color: var(--light-blue);
  opacity: 0.7;
  margin-right: 2rem;
}

.checkbox-check:focus {
  border: none;
}
.checkbox-check:hover {
  border: none;
  background-color: var(--light-pink);
}

.checkbox-check:checked {
  /*background-color: var(--pink);*/
  background: url("../assets/shared/desktop/icon-check.svg") no-repeat;
  background-color: var(--pink);
  background-position: center;
  opacity: 1;
}
.checkbox-label {
  color: var(--blue);
}
</style>
