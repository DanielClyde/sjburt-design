<script setup lang="ts">
const props = defineProps<{
  theme: 'light' | 'dark';
  topTitle: string;
  bottomTitle: string;
}>();
</script>

<template>
  <div class="section" :class="props.theme">
    <div class="title left">{{ props.topTitle }}</div>
    <div class="banner-wrapper left">
      <div class="left-banner"></div>
    </div>
    <slot name="default"></slot>
    <div v-if="props.bottomTitle" class="banner-wrapper right">
      <div class="right-banner"></div>
    </div>
    <div class="title right">{{ props.bottomTitle }}</div>
  </div>
</template>

<style scoped lang="scss">
$background-gradient: linear-gradient(90deg, #57ba62, #f1e31b, #f1bac4);
$background-gradient-reverse: linear-gradient(270deg, #57ba62, #f1e31b, #f1bac4);
$banner-skew-percentage: 20%;
$banner-heights: (
  'large': 210px,
  'medium': 150px,
  'small': 100px,
  'xsmall': 70px,
  'xxs': 50px,
);
$banner-skew-percent: 20%;
$text-sizes: (
  'large': 75pt,
  'medium': 50pt,
  'small': 30pt,
  'xsmall': 25pt,
  'xxs': 18pt,
);
$top-text-offset: (
  'large': -11pt,
  'medium': -6.25pt,
  'small': -4.75pt,
  'xsmall': -3pt,
  'xxs': -2pt
);
$bottom-text-offset: (
  'large': calc(-12pt - 3px),
  'medium': calc(-6.25pt - 3px),
  'small': calc(-3.75pt - 3px),
  'xsmall': calc(-3pt - 3px),
  'xxs': calc(-2pt - 3px),
);
.title {
  font-size: map-get($map: $text-sizes, $key: 'large');
  line-height: map-get($map: $text-sizes, $key: 'large');
  color: #666666;
  font-weight: bold;
  text-shadow: -3px 3px 3px rgba(0, 0, 0, 0.3);
  position: absolute;
  z-index: 2;
  font-family: 'swissck';
  &.left {
    top: map-get($map: $top-text-offset, $key: 'large');
    left: 10px;
  }
  &.right {
    bottom: map-get($map: $bottom-text-offset, $key: 'large');
    right: 10px;
  }
}

.section-content {
  width: 100%;
  min-height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: black;
}

.banner-wrapper {
  background: transparent;
  height: map-get($map: $banner-heights, $key: 'large');
  width: 100%;

  z-index: 1;
  &.left {
    filter: drop-shadow(0px 5px 2px rgba(0, 0, 0, 0.3));
    position: absolute;
    top: 0;
    left: 0;
  }
  &.right {
    position: absolute;
    bottom: 0;
    right: 0;
  }
}
.left-banner {
  background: $background-gradient;
  height: map-get($map: $banner-heights, $key: 'large');
  clip-path: polygon(0% 0%, 100% 0%, 100% $banner-skew-percent, 0% 100%);
}
.right-banner {
  background: $background-gradient-reverse;
  height: map-get($map: $banner-heights, $key: 'large');
  clip-path: polygon(0% calc(100% - $banner-skew-percent), 100% 0%, 100% 100%, 0% 100%);
}

.section {
  height: fit-content;
  position: relative;
  overflow: hidden;
  &.light {
    background-color: white;
  }
  &.dark {
    background-color: #666666;
  }
}

@media screen and (max-width: 1200px) {
  .title {
    font-size: map-get($map: $text-sizes, $key: 'medium');
    line-height: map-get($map: $text-sizes, $key: 'medium');
    &.left {
      top: map-get($map: $top-text-offset, $key: 'medium');
    }
    &.right {
      bottom: map-get($map: $bottom-text-offset, $key: 'medium');
    }
  }
  .left-banner {
    height: map-get($map: $banner-heights, $key: 'medium');
  }
  .right-banner {
    height: map-get($map: $banner-heights, $key: 'medium');
  }
  .banner-wrapper {
    height: map-get($map: $banner-heights, $key: 'medium');
  }
}

@media screen and (max-width: 800px) {
  .title {
    font-size: map-get($map: $text-sizes, $key: 'small');
    line-height: map-get($map: $text-sizes, $key: 'small');
    &.left {
      top: map-get($map: $top-text-offset, $key: 'small');
    }
    &.right {
      bottom: map-get($map: $bottom-text-offset, $key: 'small');
    }
  }
  .left-banner {
    height: map-get($map: $banner-heights, $key: 'small');
  }
  .right-banner {
    height: map-get($map: $banner-heights, $key: 'small');
  }
  .banner-wrapper {
    height: map-get($map: $banner-heights, $key: 'small');
  }
}

@media screen and (max-width: 575px) {
  .title {
    font-size: map-get($map: $text-sizes, $key: 'xsmall');
    line-height: map-get($map: $text-sizes, $key: 'xsmall');
    &.left {
      top: map-get($map: $top-text-offset, $key: 'xsmall');
    }
    &.right {
      bottom: map-get($map: $bottom-text-offset, $key: 'xsmall');
    }
  }
  .left-banner {
    height: map-get($map: $banner-heights, $key: 'xsmall');
  }
  .right-banner {
    height: map-get($map: $banner-heights, $key: 'xsmall');
  }
  .banner-wrapper {
    height: map-get($map: $banner-heights, $key: 'xsmall');
  }
}

@media screen and (max-width: 380px) {
  .title {
    font-size: map-get($map: $text-sizes, $key: 'xxs');
    line-height: map-get($map: $text-sizes, $key: 'xxs');
    &.left {
      top: map-get($map: $top-text-offset, $key: 'xxs');
    }
    &.right {
      bottom: map-get($map: $bottom-text-offset, $key: 'xxs');
    }
  }
  .left-banner {
    height: map-get($map: $banner-heights, $key: 'xxs');
  }
  .right-banner {
    height: map-get($map: $banner-heights, $key: 'xxs');
  }
  .banner-wrapper {
    height: map-get($map: $banner-heights, $key: 'xxs');
  }
}
</style>
