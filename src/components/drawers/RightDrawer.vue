<template>
  <q-list>
    <q-item>
      <q-btn flat dense @click="$q.fullscreen.toggle()">
        <q-icon :name="$q.fullscreen.isActive ? 'fullscreen_exit' : 'fullscreen'"/>
      </q-btn>
    </q-item>
    <q-item>
      <q-btn flat dense @click="$store.commit('walle/setShowWallE', true)">
        <img class="img-logo" :src="require('../../assets/wall-e.png')">
      </q-btn>
    </q-item>
  </q-list>
</template>
