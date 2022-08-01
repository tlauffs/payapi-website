<script setup lang="ts">
</script>

<template>
  <div class="mt-3">
    <div class="overflow-wrapper top-wrapper">
      <div class="circle top-sec-circle"></div>
    </div>
    <div class="section mt">
      <h2 class="flex-md-center h2-big">Pricing</h2>
      <div class="pricing-grid">
        <div class="flex-md-center">
          <h3 class="mt">Free Plan</h3>
        </div>
        <div>
          <p class="text-md-center">
            Build and test using our core set of products with up to 100 API
            requests
          </p>
        </div>
        <div class="flex-md-center">
          <h2 class="mb">$0.00</h2>
          <div class="divider-light"></div>
          <div class="pricing-list">
            <ul class="check">
              <li>Transactions</li>
              <li>Auth</li>
              <li>Identity</li>
            </ul>
            <ul class="no-check">
              <li>Investments</li>
              <li>Assets</li>
              <li>Liabilities</li>
              <li>Income</li>
            </ul>
          </div>
          <div class="divider-light"></div>
          <button class="btn-sec mt-2"><b>Request Access</b></button>
        </div>
        <div class="flex-md-center">
          <h3 class="mt">Basic Plan</h3>
        </div>
        <div>
          <p class="text-md-center">
            Launch your project with unlimited requests and no contractual
            minimums
          </p>
        </div>
        <div class="flex-md-center">
          <h2 class="mb">$249.00</h2>
          <div class="divider-light"></div>
          <div class="pricing-list">
            <ul class="check">
              <li>Transactions</li>
              <li>Auth</li>
              <li>Identity</li>
              <li>Investments</li>
              <li>Assets</li>
            </ul>
            <ul class="no-check">
              <li>Liabilities</li>
              <li>Income</li>
            </ul>
          </div>
          <div class="divider-light"></div>
          <button class="btn-sec mt-2"><b>Request Access</b></button>
        </div>
        <div class="flex-md-center">
          <h3 class="mt">Premium Plan</h3>
        </div>
        <div>
          <p class="text-md-center">
            Get tailored solutions, volume pricing, and dedicated support for
            your team
          </p>
        </div>
        <div class="flex-md-center">
          <h2 class="mb">$499.00</h2>
          <div class="divider-light"></div>
          <div class="pricing-list">
            <ul class="check">
              <li>Transactions</li>
              <li>Auth</li>
              <li>Identity</li>
              <li>Investments</li>
              <li>Assets</li>
              <li>Liabilities</li>
              <li>Income</li>
            </ul>
          </div>
          <div class="divider-light"></div>
          <button class="btn-sec mt-2"><b>Request Access</b></button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.pricing-grid {
  display: grid;
  grid-template-rows: auto auto auto;
  grid-auto-flow: column;
  gap: 1rem;
  margin: 2rem 0;
}

.pricing-list {
  margin: 1.5rem 0;
}

@media (max-width: 48rem) {
  .pricing-grid {
    grid-template-rows: repeat(9, auto);
  }
}

h3 {
  color: var(--pink);
}

ul {
  margin: 0;
  padding-left: 1.5rem;
}

li {
  margin: 0.8rem 0;
  color: var(--blue);
}
ul.no-check > li {
  opacity: 0.5;
}

ul.check {
  list-style-image: url("../assets/shared/desktop/icon-check.svg");
}
ul.no-check {
  list-style-type: none;
}
</style>
