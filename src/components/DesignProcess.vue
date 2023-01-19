<template>
  <div class="text-lg design-process-title">simple design process</div>
  <div class="design-process-container">
    <div class="design-process-section">
      <div class="design-process-image">
        <img src="../assets/consultation.svg" />
      </div>
      <div class="design-process-title text-med">free site visit &amp; consultation</div>
      <ul class="text-xs design-process-list">
        <li>discuss design needs, preferences, and challenges</li>
        <li>walk, analyze, photograph and measure the site as needed</li>
        <li>discuss timeline goals, set concept and final design deadlines</li>
        <li>establish design fee based on project size and complexity</li>
      </ul>
    </div>
    <div class="design-process-section">
      <div class="design-process-image">
        <img src="../assets/concept-plan.svg" />
      </div>
      <div class="design-process-title text-med">concept plan &amp; review</div>
      <ul class="text-xs design-process-list">
        <li>review concept plans, renderings and design ideas to ensure the design is in line with the clients needs</li>
        <li>note corrections and edits to the design for the final design</li>
        <li>review established deadlines and adjust if necessary</li>
      </ul>
    </div>
    <div class="design-process-section">
      <div class="design-process-image">
        <img src="../assets/final-design-documents.svg" />
      </div>
      <div class="design-process-title text-med">final design &amp; documents</div>
      <ul class="text-xs design-process-list">
        <li>repeat concept plan review and edit process as needed until a satisfactory design is reached</li>
        <li>final plans, renderings and other deliverables handed over to the client to be taken to a contractor for construction</li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">

.design-process-list {
  color: #666666;
  font-family: 'swissl';
}
$banner-heights: (
  'large': 210px,
  'medium': 150px,
  'small': 100px,
  'xsmall': 70px,
  'xxs': 50px,
);
.design-process-title {
  text-align: center;
  color: #444444;
  font-family: 'swissl';
  margin-top: 20px;
}
.design-process-container {
  display: flex;
  justify-content: space-evenly;
  padding: 25px 15px;
  margin-bottom: map-get($map: $banner-heights, $key: 'large');
}

.design-process-section {
  margin: 0px 10px;
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.design-process-image {
  width: 100%;
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  img {
    max-width: 75%;
    max-height: 100%;
  }
}

@media screen and (max-width: 1200px) {
  .design-process-container {
    margin-bottom: map-get($map: $banner-heights, $key: 'medium');
  }
  .design-process-image {
    height: 170px;
  }
}

@media screen and (max-width: 800px) {
  .design-process-container {
    margin-bottom: map-get($map: $banner-heights, $key: 'small');
  }
  .design-process-image {
    height: 120px;
  }
}

@media screen and (max-width: 575px) {
  .design-process-container {
    margin-bottom: map-get($map: $banner-heights, $key: 'xsmall');
    flex-direction: column;
  }
  .design-process-image {
    height: 90px;
    width: 140px;
    margin-top: 20px;
  }
}

@media screen and (max-width: 380px) {
  .design-process-container {
    margin-bottom: map-get($map: $banner-heights, $key: 'xxs');
  }
}
</style>
