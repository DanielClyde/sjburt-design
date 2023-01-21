<template>
  <div class="collage-container">
    <div class="collage-section">
      <div class="collage-image"></div>
      <div class="collage-image"></div>
      <div>
        <div class="collage-image"></div>
        <div class="collage-image"></div>
      </div>
      <!-- <img src="../assets/design-gallery/gallery-1.png" /> -->
    </div>
    <div class="collage-section">
      <div class="collage-image"></div>
      <!-- <img src="../assets/design-gallery/gallery-2.png" /> -->
    </div>
    <div class="collage-section">
      <div class="collage-image"></div>
      <div class="collage-image"></div>
      <div class="collage-image"></div>
      <!-- <img src="../assets/design-gallery/gallery-8.png" /> -->
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.collage-container {
  background-color: #666666;
  width: 100%;
  overflow-x: auto;
  margin: 18px 0px;
  height: 750px;
  display: grid;
  grid-template-rows: 1.2fr 1fr;
  grid-template-columns: 2fr 1fr;
  grid-template-areas:
    'one two'
    'three two';
}

.collage-section {
  img {
    max-width: 100%;
    max-height: 100%;
  }
}
.collage-section:nth-child(1) {
  grid-area: one;
  display: flex;
  min-width: 600px;
  > :nth-child(1) {
    flex: 1;
    background-image: url('../assets/design-gallery/gallery-1.png');
  }
  > :nth-child(2) {
    flex: 0.7;
    background-image: url('../assets/design-gallery/gallery-2.png');
  }
  > :nth-child(3) {
    flex: 0.5;
    display: flex;
    flex-direction: column;
    > :nth-child(1) {
      background-image: url('../assets/design-gallery/gallery-8.png');
      flex: 1;
    }

    > :nth-child(2) {
      flex: 1;
      background-image: url('../assets/design-gallery/gallery-7.png');
    }
  }
}
.collage-section:nth-child(2) {
  grid-area: two;
  display: flex;
  min-width: 270px;
  div {
    background-image: url('../assets/design-gallery/gallery-3.png');
    flex: 1;
  }
}
.collage-section:nth-child(3) {
  grid-area: three;
  display: flex;
  min-width: 600px;
  :nth-child(1) {
    background-image: url('../assets/design-gallery/gallery-6.png');
    flex: 1;
  }
  :nth-child(2) {
    flex: 0.8;
    background-image: url('../assets/design-gallery/gallery-4.png');
  }
  :nth-child(3) {
    flex: 1.2;
    background-image: url('../assets/design-gallery/gallery-5.png');
  }
}

.collage-image {
  margin: 7px;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

@media screen and (max-width: 1200px) {
  .collage-container {
    height: 600px;
  }
}

@media screen and (max-width: 1000px) {
  .collage-container {
    height: 500px;
  }
}

@media screen and (max-height: 600px) {
  .collage-container {
    height: 400px;
  }
}
</style>
