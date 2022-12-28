<script setup>
import { ref } from 'vue'
import IconPlus from '../components/icons/IconPlus.vue'

const sections = ref([
  {
    q: '123',
    a: '123456789',
    open: false
  },
  {
    q: '123',
    a: '123456789',
    open: false
  }
])

const closeAllFields = (item) => {
  if (!item.open) {
    sections.value.forEach((el) => (el.open = false))
  }
  item.open = !item.open
}
</script>

<template>
  <div class="wrapper">
    <div class="field-wrapper">
      <div class="field" v-for="(section, i) in sections" :key="i">
        <div class="open-field" @click="closeAllFields(section)">
          <h3>
            {{ section.q }}
            <IconPlus class="icon" :class="section.open ? 'rotate' : ''" />
          </h3>
          <p class="invisible" :class="section.open ? 'visible' : ''">
            {{ section.a }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.wrapper {
  text-align: center;
  max-width: 500px;
  margin: 40px auto;
}

.field {
  border: 1px solid gray;
  margin: 10px 0;
}

.field-wrapper {
  margin-top: 20px;
}

.invisible {
  visibility: hidden;
  opacity: 0;
  height: 0;
  transition: opacity 0.3s, height 0.3s, visibility 0.3s;
}

.visible {
  visibility: visible;
  height: 70px;
  opacity: 1;
  padding: 10px 20px;
}

h3 {
  display: flex;
  align-items: center;
  justify-content: space-around;
  padding: 18px 24px;
  margin: 8px 0;
}

.rotate {
  transform: rotate(45deg);
  transition: transform 0.3s;
}

.icon {
  transition: transform 0.3s;
}
</style>
