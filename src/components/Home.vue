<script setup lang="ts">

</script>
<template>
    <div>
    <div class="circle top"></div>
    </div>
    <div class="grid-container section">
        <div class="grid-item header-text">
            <h1>Start building with our APIs for absolutely free.</h1>
            <div class="input-wrapper demo-input">
                <input class="input" placeholder="Enter email address " type="text">
                <button class="btn-primary btn-demo">Schedule a Demo</button>
            </div>
            <p  class="indent">Have any questions?  <router-link to="/contact" class="btn-link"><b>Contact Us</b></router-link></p>
        </div>
        <div class="grid-item phone-item">
            <img src="/src/assets/home/desktop/illustration-phone-mockup.svg" class="phone-img" alt="">
        </div>
    </div>
    <div class="dark-section">
        <div class="grid-container">
        <div class="section-who">
            <h2 class="white-text">Who we work with</h2>
            <p class="white-text opaque">Today, millions of people around the world have successfully connected 
    their accounts to apps they love using our API. We provide developers 
    with the tools they need to create easy and accessible experiences 
    for their users.</p>
            <div class="mt-3 mb">
                <router-link to="/about" class="btn-sec-light">About Us</router-link>
            </div>
        </div>
        <div class="logo-grid-wrapper">
            <div class="logo-grid">
                <div><img src="/src/assets/shared/desktop/tesla.svg" alt=""></div>
                <div><img src="/src/assets/shared/desktop/microsoft.svg" alt=""></div>
                <div><img src="/src/assets/shared/desktop/hewlett-packard.svg" alt=""></div>
                <div><img src="/src/assets/shared/desktop/oracle.svg" alt=""></div>
                <div><img src="/src/assets/shared/desktop/google.svg" alt=""></div>
                <div><img src="/src/assets/shared/desktop/nvidia.svg" alt=""></div>
            </div>
        </div>
    </div>
    </div>

    Easy to implement
    Our API comes with just a few lines of code. You’ll be up and running in 
    no time. We built our documentation page to integrate payments functionality 
    with ease.

    Simple UI & UX
    Our pre-built form is easy to integrate in your app or website’s checkout 
    flow and designed to optimize conversion.

    Personal Finances
    Consolidate financial data from multiple sources and categorize transactions up to
    2 years of history. Analyze reports to reconcile activities in your account.

    Banking & Coverage
    With our platform, you can speed up account onboarding and support ongoing payments 
    for checking, savings, credit card, and brokerage accounts.

    Consumer Payments
    It’s easier to set up secure bank payments with us through a flow designed with the 
    user experience in mind. Customers could instantly authenticate their account.

    Ready to start? 
    Enter email address 
    Schedule a Demo

    Pricing
    About
    Contact
</template>

<style scoped>
.top{
    position: absolute;
    overflow: hidden;
    top:-12rem;
    right:-12rem;
}

.grid-container {
    display: grid;
    align-items: center;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 1fr;
    grid-column-gap: 0px;
    grid-row-gap: 0px;
}
.grid-item{
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.phone-img{
    margin-left: clamp(0px,15%,120px);
    max-width: clamp(0rem,50rem,100%);
}
.header-text {
    margin-bottom: 5rem;
}
.demo-input{
    margin-top: 2rem;
}
.logo-grid {
    --n: 3;
    display: grid;
    grid-template-columns: repeat(auto-fill,
           minmax(max(10rem,(100% - (var(--n) - 1)*1rem)/var(--n)), 1fr));
    gap: 1rem;
    justify-items: center;
    align-items: center;
}

.logo-grid-wrapper {
    width: 100%;
}
.section-who {
    max-width:28rem;
}
/* responsiveness query */
@media (max-width: 64rem) {
    .grid-container {
        grid-template-columns: 1fr;
        grid-template-rows: 2;
        justify-items: center;
        text-align: center;
    }
    .phone-img{
        margin: 0 auto;
        padding-left: 8%;
        max-width: clamp(0rem,25rem,100%);
    } 
    .phone-item{
        grid-row: 1;
    } 
    .demo-input{
        margin-left: auto;
        margin-right: auto;
    }
    .top{
        top:calc(-100vw - 20rem);
        left: 50%;
        transform: translate(-50%, 0);
    }
    .logo-grid-wrapper {
        grid-row: 1;
        margin-bottom: 4rem;
    }
}
</style>
