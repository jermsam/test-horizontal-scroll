<template>
  <q-page class="column flex-center">
    <q-knob
      v-model="count"
      :min="min"
      :max="max"
      size="80px"
      show-value
      :thickness="0.13"
      color="primary"
      track-color="dark"
    >
      <q-avatar size="75px">
        <img alt="Quasar logo" src="~assets/quasar-logo-inner.svg" />
      </q-avatar>
    </q-knob>

    {{ { x, y, isScrolling, arrivedState, directions } }}
    <div class="q-mt-xl">
      <q-btn
        color="primary"
        dense
        round
        label="-"
        :disable="count === min"
        @click="count--"
      />

      <span class="q-mx-md text-bold">{{ count }}</span>

      <q-btn
        color="primary"
        dense
        round
        label="+"
        :disable="count === max"
        @click="count++"
      />
    </div>

    <div class="q-mt-md" style="width: 200px">
      <q-slider v-model="count" :min="min" :max="max" />
    </div>
    <div class="hor-scroll q-gutter-sm full-width" ref="el">
      <q-btn
        v-for="(b, i) in names"
        :key="i"
        :label="b"
        color="primary"
        class="item"
      />
    </div>
  </q-page>
</template>

<script setup>
import { ref, onBeforeUpdate } from 'vue';
import { useScroll } from '@vueuse/core';

const count = ref(0);
const el = ref(null);

onBeforeUpdate(() => {
  el.value = null;
});

const { x, y, isScrolling, arrivedState, directions } = useScroll(el);

let names = ref([
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
  'paul',
  'James',
  'John',
  'Peter',
  'Mathew',
  'Mark',
  'Judas',
]);

const min = -5;
const max = 5;
</script>
<style scoped lang="scss">
.hor-scroll {
  overflow: auto;
  white-space: nowrap;
  background: #d7d7d7d7;
  .q-btn {
    display: inline-block;
  }
}
</style>
