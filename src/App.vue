<template>
  <div>
    <SelectArtist @artist-selected="artistSelected($event)"></SelectArtist>
    <SongList v-if="selectedArtist !== null" :artistId="selectedArtist"></SongList>
  </div>
</template>

<script setup>
  import { ref } from 'vue';
  import SelectArtist from './components/SelectArtist.vue';
  import SongList from './components/SongList.vue';
  
  const selectedArtist = ref(null);
  
  function artistSelected(artistId) {
    selectedArtist.value = artistId;
  } 
</script>

<style lang="scss" scoped></style>