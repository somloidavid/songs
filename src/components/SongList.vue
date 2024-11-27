<template>
    <div>
        <table class="table">
            <thead>
                <tr>
                    <th></th>
                    <th>Title</th>
                    <th scope="col">Year</th>
                    <th scope="col">Time</th>
                    <th scope="col">BPM</th>
                    <th scope="col">Genre</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="song in filteredSongs" :key="song._id">
                    <td>{{ counter++ }}</td>
                    <td>{{ song.TITLE }}</td>
                    <td>{{ song.YEAR }}</td>
                    <td>{{ song.TIME }}</td>
                    <td>{{ song.BPM }}</td>
                    <td>{{ song.GENRE }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup>
import songsData from '@/songs';
import { computed } from 'vue';
const props = defineProps(['artistId']);

let counter = 1;

const filteredSongs = computed(() => {
    counter = 1;
    return songsData.filter(song => song.ARTIST_ID == props.artistId);
});
</script>

<style lang="scss" scoped></style>