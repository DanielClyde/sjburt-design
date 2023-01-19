<template>
  <div class="about-section">
    <div class="family-photo">
      <img src="../assets/family.png" />
    </div>
    <div class="about-text text-xs">
      After graduating from Utah State University with a Bachelor’s in Landscape
      Architecture, I moved with my young family to South Lake Tahoe to work as a
      Landscape Designer with Design Workshop. After two years next to the that crystal
      clear lake, we moved back to take a job as the Community Development Director, City
      Planner, with North Logan City. Four years with North Logan City and the time came
      to shift more back into Landscape and Graphic Design. All of the experience gained
      working on projects large and small with Design Workshop, and working closely with
      municipal government and city ordinances with North Logan, translate into smart,
      clear, and beautiful designs to fit any needs.
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.about-section {
  background: #666666;
  padding: 15px 0px;
  display: flex;
  align-items: center;
  justify-content: space-around;
}
.family-photo {
  display: flex;
  align-items: center;
  justify-content: center;
  flex: .33;
  padding: 0px 15px;
  img {
    max-width: 100%;
  }
}
.about-text {
  padding: 0px 15px;
  flex: 1;
  color: white;
}

@media screen and (max-width: 1000px) {
  .family-photo {
    flex: .5;
  }

}


@media screen and (max-width: 1000px) {
  .about-section {
    flex-direction: column;
  }
  .family-photo {
    margin-bottom: 20px;
    flex: .25;
    height: 200px;
    img {
      max-height: 100%;
    }
  }

}
</style>
