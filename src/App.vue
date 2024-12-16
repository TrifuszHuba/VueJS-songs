<template>
  <div id="container">
    <ArtistSelect @artist-selected="artistSelected($event)"></ArtistSelect>
    <SongList v-if="selectedArtist !== null" :artistId="selectedArtist"></SongList>
  </div>
</template>

<script>
import ArtistSelect from './components/ArtistSelect.vue';
import SongList from './components/SongList.vue';

export default {
  name: 'App',
  components: {
    ArtistSelect,
    SongList,
  },
  data() {
    return {
      selectedArtist: null,
    };
  },
  methods: {
    artistSelected(artistId) {
      this.selectedArtist = artistId !== 'null' ? artistId : null;
    },
  },
};
</script>

<style scoped>
  #container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>