<script setup lang="ts">
import About from './components/About.vue';
import Contact from './components/Contact.vue';
import DesignGallery from './components/DesignGallery.vue';
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
    <DesignGallery></DesignGallery>
    <Section theme="light" top-title="GRAPHIC DESIGN" bottom-title="ABOUT">
      <div class="graphic-design-photo">
        <img src="./assets/graphic-design-galley.png" />
      </div>
    </Section>
    <About></About>
    <Section theme="light" :hideBanner="true" top-title="CONTACT">
      <Contact></Contact>
    </Section>
  </div>
</template>

<style scoped lang="scss">
.graphic-design-photo {
  width: 100%;
  text-align: center;
  padding: 150px 0px 200px 0px;
  img {
    max-height: 100%;
    max-width: 90%;
  }
}

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

@media screen and (max-width: 800px) {
  .graphic-design-photo {
    width: 100%;
    overflow-x: auto;
    padding: 100px 20px 120px 20px;
    img {
      max-width: unset;
      max-height: 500px;
    }
  }
}

@media screen and (max-width: 600px) {
  .graphic-design-photo {
    width: 100%;
    overflow-x: auto;
    padding: 80px 20px 100px 20px;
    img {
      max-width: unset;
      max-height: 400px;
    }
  }
}
</style>
