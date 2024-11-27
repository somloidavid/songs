<template>
    <div>
        <select name="artists" id="artists" @change="artistSelected">
            <option value="null">Válassz egy előadót</option>
            <option v-for="artist in artistData" :key="artist.id" :value="artist._id">{{ artist.artist }}</option>
        </select>
    </div>
</template>

<script setup>
import artistData from '@/artists';
import { defineEmits } from 'vue';

const emit = defineEmits(['artist-selected']);
const artistSelected = (event) => {
    const artistId = event.target.value;
    emit('artist-selected', artistId);
};
</script>

<style lang="scss" scoped></style>