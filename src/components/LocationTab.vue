<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'
import { motion } from 'motion-v'
import { Cursor } from 'motion-plus-vue'
import LocationGrid from '@/components/LocationGrid.vue'

const isHovering = ref(false)
const isOpen = ref(false)
const setIsHovering = (v: boolean) => (isHovering.value = v)
const toggle = () => (isOpen.value = !isOpen.value)

// Close on Escape
function onKey(e: KeyboardEvent){
  if(e.key === 'Escape' && isOpen.value) isOpen.value = false
}
onMounted(()=> window.addEventListener('keydown', onKey))
onBeforeUnmount(()=> window.removeEventListener('keydown', onKey))
</script>

<template>
  <div class="dropdown-wrap">
    <!-- Custom cursor text -->
    <teleport to="body">
      <Cursor class="app-cursor">
        <span v-if="isHovering && !isOpen" class="cursor-caption">View Location</span>
        <span v-else-if="isHovering && isOpen" class="cursor-caption">Close</span>
      </Cursor>
    </teleport>

    <!-- Tab button -->
    <button
      class="dropdown-tab"
      type="button"
      :aria-expanded="isOpen"
      @mouseenter="setIsHovering(true)"
      @mouseleave="setIsHovering(false)"
      @click="toggle"
    >
      <span class="tab-label">Locations</span>
      <span class="tab-chevron" :class="{ open: isOpen }">▾</span>
    </button>

    <!-- Animated panel -->
    <motion.div
      v-if="isOpen"
      class="panel card"
      :initial="{ opacity: 0, y: -8, scaleY: 0.96, transformOrigin: 'top' }"
      :animate="{ opacity: 1, y: 0, scaleY: 1, transition: { duration: 0.35 } }"
      :exit="{ opacity: 0, y: -8, scaleY: 0.96, transition: { duration: 0.25 } }"
    >
      <LocationGrid />
    </motion.div>
  </div>
</template>

<style scoped>

.app-cursor{
  position: fixed;                 /* detach from local ancestors */
  z-index: 2147483647 !important;  /* always on top */
  pointer-events: none !important; /* never block clicks */
}
.cursor-caption{
  position: absolute;
  transform: translate(18px,-18px);
  white-space: nowrap;
  padding: 6px 10px;
  border-radius: 999px;
  font-weight: 600;
  font-size: 14px;
  line-height: 1;
  color: bisque;
  background: rgb(0, 0, 0);
  box-shadow: 0 6px 18px rgba(0,0,0,.25);
}

/* Cursor bubble */
.cursor {
  background-color: var(--accent) !important;
  border-radius: 999px !important;
  padding: 6px 10px !important;
  box-shadow: 0 6px 18px rgba(0,0,0,0.25) !important;
}

/* Tab */
.dropdown-tab {
  width: 100%;
  font-family: 'Times New Roman', Times, serif;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  padding: 16px 18px;
  border-radius: 14px;
  border: 1px solid rgba(255,255,255,0.12);
  background: linear-gradient(180deg, rgba(31, 22, 18, 0.85), rgba(0,0,0,0.1));
  color: bisque;
  cursor: pointer;
  transition: border-color .25s ease, transform .15s ease, background .25s ease;
}
.dropdown-tab:hover { border-color: var(--accent); transform: translateY(0px); }
.tab-label { font-size: 1.2rem; letter-spacing: .5px; }
.tab-chevron { transition: transform .25s ease; }
.tab-chevron.open { transform: rotate(180deg); }

/* Panel */
.panel { margin-top: 12px; padding: 16px; border-radius: 16px; }
</style>
