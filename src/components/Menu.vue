<template>
  <div class="background" @click.self.stop="$emit('dismiss')">
    <TransitionGroup appear name="slide">
      <div @click.self.stop="$emit('dismiss', b.sectionId)" :key="b.sectionId" class="text-sm link" v-for="b of buttons">{{ b.label }}</div>
    </TransitionGroup>
  </div>
</template>

<script setup lang="ts">
import { onMounted, onBeforeUnmount } from 'vue';

function onScroll() {
  window.scrollTo({ left: 0, top: 0});
}

onMounted(() => {
  window.addEventListener('scroll', onScroll);
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', onScroll);
})
defineEmits<{ (e: 'dismiss', link?: string): void }>();
const buttons = [
  { label: 'Landscape Design', sectionId: 'landscapeDesign' },
  { label: 'Graphic Design', sectionId: 'graphicDesign' },
  { label: 'About', sectionId: 'about' },
  { label: 'Contact', sectionId: 'contact' },
]
</script>

<style scoped lang="scss">
.link {
  width: fit-content;
  color: white;
  margin: 15px 0px;
  &:hover {
    cursor: pointer;
    color: #ababab;
  }
}
.slide-enter-from,
.slide-leave-to {
  transform: translateY(20px);
  opacity: 0;
}

.slide-enter-active,
.slide-leave-active {
  transition: all 0.4s ease-out;
}
.background {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.7);
  backdrop-filter: blur(8px);
  display: flex;
  flex-direction: column;
  padding: 50px;
  align-items: center;
}
</style>
