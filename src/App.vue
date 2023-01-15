<script setup lang="ts">
import DesignProcess from './components/DesignProcess.vue';
import LandingSection from './components/LandingSection.vue';
import Section from './components/Section.vue';
</script>

<template>
  <div>
    <LandingSection></LandingSection>
    <Section theme="light" top-title="LANDSCAPE DESIGN" bottom-title="DESIGN GALLERY">
      <div class="landscape-photo">
        <img style="width: 100%" src="./assets/landscaping-house-export.png" />
      </div>
      <DesignProcess></DesignProcess>
    </Section>
    <div class="spacer dark"></div>
  </div>
</template>

<style scoped lang="scss">
.landscape-photo {
  width: 100%;
  background: url('./assets/landscaping-house-export.png');
  background-size: cover;
  background-repeat: no-repeat;
}
.spacer {
  background-color: white;
  height: 300px;
  position: relative;
  &.dark {
    background-color: #666666;
  }
}
</style>
