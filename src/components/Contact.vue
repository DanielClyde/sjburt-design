<template>
  <div class="contact-section">
    <div class="invisible"></div>
    <div class="contact-text">
      <div class="text-sm">
        For an on site consultation or any other design needs, Call or email Spencer at
      </div>
      <div class="text-med">
        <a href="tel: 435.764.7838">435.764.7838</a>
      </div>
      <div class="text-med">
        <a href="mailto: sjburtdesign@gmail.com">sjburtdesign@gmail.com</a>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.invisible {
  color: transparent;
  opacity: 0;
  min-width: 30%;
}
.contact-section {
  padding: 20px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.contact-text {
  margin-left: 50px;
  > :nth-child(2) {
    margin-top: 20px;
  }
}
a {
  color: #444444;
  text-decoration: none;
  font-style: normal;
  cursor: pointer;
  &:hover {
    color: #666666;
  }
  &:active {
    color: #444444;
  }
}

</style>
