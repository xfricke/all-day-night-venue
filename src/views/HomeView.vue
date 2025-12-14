<template>
  <div>
    <section class="section">
      <landingBanner />
    </section>
    <section class="section">
      <IntroSection />
    </section>
    <section class="section">
    <div class="container row-tiles">
      <div class="tile"><MenuTab /></div>
      <div class="tile"><LocationTab /></div>
    </div>
  </section>
  <section class="section">
    <SevenSeedsSection />
  </section>
  <section>
    <UpcomingDJ />
  </section>
  <section>
    <OutOfOffice />
  </section>
  <section>
    <FoodSection />
  </section>
  </div>
  <SiteFooter />
</template>

<script setup>
import MenuTab from '@/components/MenuTab.vue'
import landingBanner from '@/components/landingBanner.vue';
import LocationTab from '@/components/LocationTab.vue';
import IntroSection from '@/components/IntroSection.vue';
import SevenSeedsSection from '@/components/SevenSeedsSection.vue'
import UpcomingDJ from '@/components/UpcomingDJ.vue';
import OutOfOffice from '@/components/OutOfOffice.vue';
import FoodSection from '@/components/FoodSection.vue';
import SiteFooter from '@/components/Footer.vue'

</script>


<style>
html{
  background-color: rgb(45, 43, 32);
}

body{
  margin: 0px;
}

.row-tiles {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.tile {
  display: flex;
  flex-direction: column;
  gap: 12px;
}


</style>

