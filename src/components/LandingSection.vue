<script setup lang="ts">
import { gsap } from 'gsap';
import { DrawSVGPlugin } from 'gsap/DrawSVGPlugin';
import { onMounted } from 'vue';

onMounted(() => {
  gsap.registerPlugin(DrawSVGPlugin);
  const tl = gsap.timeline();
  tl.from('#letters', { opacity: 0, duration: 3 }, 0);
  tl.from('svg', { scale: 1.3, duration: 2.5 }, 0);
  tl.from('#border', { drawSVG: '0', duration: 2 }, 1);
  tl.from('#signature', { opacity: 0, y: '-15px', duration: 1 }, 3);
  tl.from('#home-btn', { opacity: 0, duration: 1 }, 3.5);
  tl.from('#contact-info', { opacity: 0, duration: 1 }, 3.5);
  tl.totalDuration(4);
  tl.play();
});

defineEmits(['menuClick']);
</script>

<template>
  <div class="landing-section">
    <img
      id="home-btn"
      src="../assets/home-btn.svg"
      class="menu-button"
      @click="$emit('menuClick')"
    />
    <svg
      class="logo"
      viewBox="0 0 463 546"
      version="1.1"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
    >
      <defs>
        <linearGradient
          x1="0.450448155%"
          y1="100%"
          x2="99.5495518%"
          y2="0%"
          id="linearGradient-koomknanwt-1"
        >
          <stop stop-color="#57BA62" offset="0%"></stop>
          <stop stop-color="#F1E31B" offset="51%"></stop>
          <stop stop-color="#F1BAC4" offset="100%"></stop>
        </linearGradient>
      </defs>
      <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
        <g id="Artboard" transform="translate(-290.000000, -140.000000)">
          <g id="brand" transform="translate(301.000000, 151.000000)">
            <g
              id="letters"
              transform="translate(61.030000, 26.710000)"
              fill="#FFFFFF"
              fill-rule="nonzero"
            >
              <path
                d="M125.44,233.85 C163.85,257.26 178.25,273.46 178.25,307.67 C178.25,347.88 139.84,382.69 94.23,382.69 C81.63,382.69 64.22,382.09 50.42,377.29 C36.02,372.49 29.42,371.89 22.81,371.89 C15.61,371.89 12.01,373.09 8.41,379.09 L0.61,379.09 L0.61,284.87 L10.21,284.87 C22.81,343.08 45.02,369.49 86.43,369.49 C117.04,369.49 136.24,349.69 136.24,325.08 C136.24,306.48 124.24,290.87 104.43,280.07 L72.02,262.07 C22.21,234.46 1.42108547e-14,205.66 1.42108547e-14,175.05 C1.42108547e-14,127.64 33.61,101.23 82.82,101.23 C97.22,101.23 110.43,101.83 123.03,107.83 C129.63,110.83 135.63,112.63 139.83,112.63 C142.23,112.63 144.63,112.03 149.43,106.63 L156.03,106.63 L159.03,188.25 L150.03,188.25 C136.23,134.24 118.22,114.43 82.22,114.43 C56.41,114.43 37.21,127.03 37.21,155.24 C37.21,168.44 46.21,185.85 63.02,196.05 L125.43,233.86 L125.44,233.85 Z"
                id="Path"
              ></path>
              <path
                d="M318.68,376.68 C318.68,461.9 283.27,507.51 216.66,507.51 C184.25,507.51 160.85,493.71 160.85,474.5 C160.85,461.3 171.65,451.09 185.46,451.09 C195.06,451.09 203.46,456.49 214.27,470.29 C224.47,482.89 230.47,487.09 239.48,487.09 C247.88,487.09 256.28,482.29 259.88,476.29 C266.48,464.29 268.28,449.28 268.28,403.67 L268.28,176.22 C268.28,150.41 262.88,140.21 249.08,140.21 C243.08,140.21 234.68,140.21 225.07,142.01 L222.07,142.61 L222.07,133.01 C257.48,122.21 280.28,114.41 315.69,100.6 L318.69,102.4 L318.69,376.66 L318.68,376.68 Z M288.07,61.22 C271.27,61.22 258.06,48.02 258.06,30.61 C258.06,13.2 271.86,-2.84217094e-14 288.67,-2.84217094e-14 C305.48,-2.84217094e-14 319.28,13.8 319.28,30.61 C319.28,47.42 306.08,61.22 288.07,61.22 L288.07,61.22 Z"
                id="Shape"
              ></path>
            </g>
            <polyline
              id="border"
              stroke="url(#linearGradient-koomknanwt-1)"
              stroke-width="21"
              points="295 443 1.74860126e-15 443 0 -4.70695531e-15 441 0 441 443 395 443"
            ></polyline>
          </g>
        </g>
      </g>
    </svg>
    <div class="spacer"></div>
    <img id="signature" src="../assets/signature.svg" class="signature" />
    <div id="contact-info" class="contact text-sm">
      <a
        href="mailto: sjburtdesign@gmail.com"
        >sjburtdesign@gmail.com</a
      >
      <a
        href="tel: 435.764.7838"
        class="right"
        >435.764.7838</a
      >
    </div>
  </div>
</template>

<style scoped lang="scss">
.logo {
  max-width: 60%;
  max-height: 50%;
}
.signature {
  max-width: 70%;
}
.contact {
  display: flex;
  height: 50px;
  align-items: flex-end;
  a {
    color: white;
    text-decoration: none;
    font-style: normal;
    cursor: pointer;
    &:hover {
      color: #ABABAB;
    }
    &:active {
      color: white;
    }
    &.right {
      margin-left: 20px;
    }
  }
}

@media screen and (max-width: 575px) {
  .contact {
    height: 40px;
  }
}
.spacer {
  height: 50px;
}
.landing-section {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100vh;
  background-color: #666666;
  position: relative;
  .menu-button {
    position: absolute;
    width: 60px;
    height: 60px;
    top: 30px;
    right: 30px;
    cursor: pointer;
    &:hover {
      transform: scale(1.05);
      transition: .1s ease transform;
    }
  }
}

@media screen and (max-width: 880px) {
  .landing-section {
    .menu-button {
      width: 40px;
      height: 40px;
    }
  }
}
</style>
