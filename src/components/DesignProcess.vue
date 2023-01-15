<template>
  <div class="text-lg design-process-title">simple design process</div>
  <div class="design-process-container">
    <div class="design-process-section">
      <img src="../assets/consultation.svg" />
      <div class="design-process-title text-med">free site visit &amp; consultation</div>
    </div>
    <div class="design-process-section">
      <img src="../assets/concept-plan.svg" />
      <div class="design-process-title text-med">concept plan &amp; review</div>
    </div>
    <div class="design-process-section">
      <img src="../assets/final-design-documents.svg" />
      <div class="design-process-title text-med">final design &amp; documents</div>
    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped lang="scss">
.design-process-title {
  text-align: center;
  color: #444444;
  font-family: 'swissl';
  margin: 15px 0;
}
.design-process-container {
  height: 50vh;
  display: flex;
  justify-content: space-evenly;
  padding: 25px 15px;
}

.design-process-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  img {
    max-width: 80%;
    max-height: 80px;
  }
}

</style>
