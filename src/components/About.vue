<script setup lang="ts">
</script>

<template>
  <div class="mt-2">
    <div class="overflow-wrapper top-wrapper">
      <div class="circle top-sec-circle"></div>
    </div>
    <div class="section mt">
      <div class="section">
        <h2 class="flex-md-center header-about h2-big">
          We empower innovators by delivering access to the financial system
        </h2>
      </div>
    </div>
    <div class="info-container">
      <h3 class="flex-child-header">Our Vision</h3>
      <p class="flex-child-text">
        Our main goal is to build beautiful consumer experiences along with
        developer-friendly infrastructure. The result is an intelligent tool
        that gives everyone the ability to create amazing products that solve
        big problems. We are deeply focused on democratizing financial services
        through technology.
      </p>
    </div>
    <div class="mt-3 info-container">
      <h3 class="flex-child-header">Our Business</h3>
      <p class="flex-child-text">
        At the core of our platform is the technical infrastructure APIs that
        connect consumers. Our innovative product provides key insights for
        businesses and individuals, as well as robust reporting for traditional
        financial institutions and developers.
      </p>
    </div>
    <div>
    <div class="overflow-wrapper left-wrapper hide-md">
      <div class="circle left-circle"></div>
    </div>
    <img
      class="img-team-desktop img-team"
      src="../assets/about/desktop/image-team-members.jpg"
      alt=""
    />
    <img
      class="img-team-mobile img-team"
      src="../assets/about/mobile/image-team-members.jpg"
      alt=""
    />
    </div>
    <div class="stats-container">
      <div>
        <div class="divider-light"></div>
        <p>Team Members</p>
        <h2 class="header-stats">300+</h2>
        <div class="divider-light hide-sm"></div>
      </div>
      <div>
        <div class="divider-light hide-sm"></div>
        <p>Offices in the US</p>
        <h2 class="header-stats">3</h2>
        <div class="divider-light hide-sm"></div>
      </div>
      <div>
        <div class="divider-light hide-sm"></div>
        <p>Transactions analyzed</p>
        <h2 class="header-stats">10M+</h2>
        <div class="divider-light"></div>
      </div>
    </div>
    <div class="mt-3 info-container">
      <h3 class="flex-child-header">The Culture</h3>
      <p class="flex-child-text">
        We strongly believe there's always an opportunity to learn from each
        other outside of day-to-day work, whether it's company-wide offsites,
        internal hackathons, or co-worker meetups. We always value cross-team
        collaboration and diversity of thought, no matter the job title.
      </p>
    </div>
    <div class="mt-3 info-container">
      <h3 class="flex-child-header">The People</h3>
      <p class="flex-child-text">
        We're all passionate about building a more efficient and inclusive
        financial infrastructure together. At PayAPI, we have diverse
        backgrounds and skills.
      </p>
    </div>
  </div>
</template>

<style scoped>
.header-about {
  width: clamp(0rem, 100%, 42rem);
}

.info-container {
  display: flex;
  margin: 4rem clamp(0rem, 20.75rem, 14vw);
}

@media (max-width: 64rem) {
  .info-container {
    margin: 4rem auto;
    width: 90vw;
  }
}

.flex-child-header {
  flex: 0 0 auto;
  width: 20rem;
}
.flex-child-text {
  margin: 0;
}

@media (max-width: 48rem) {
  .info-container {
    flex-direction: column;
    text-align: center;
  }
  .flex-child-header {
    flex: 0 0 auto;
    width: 100%;
    margin-bottom: 1rem;
  }
}

.img-team {
  width: 100%;
}

@media (max-width: 48rem) {
  .img-team-desktop {
    display: none;
  }
}

@media (min-width: 48rem) {
  .img-team-mobile {
    display: none;
  }
  .img-team-desktop {
    display: block;
  }
}

.stats-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 1fr;
  gap: 2rem;
  margin: 4rem clamp(0rem, 10.375rem, 7vw);
}

@media (max-width: 64rem) {
  .stats-container {
    margin: 4rem auto;
    width: 90vw;
  }
}

@media (max-width: 48rem) {
  .stats-container {
    grid-template-columns: 1fr;
    grid-template-rows: repeat(3, 1fr);
    text-align: center;
  }
}

.header-stats {
  font-size: 3.5rem;
  color: var(--pink);
  margin-bottom: 1rem;
}
</style>
