 
<template>
    <div>
      <h1> Song List !</h1>
      <p v-for="(song, index) in songs" :key="index" @click="addToPlaylist(index)">
        {{song.artist}} - {{song.title}}
      </p>
        
        
    </div>
</template>

<script>
export default {
  name: 'SongList',
  props: {
    songs: Array
  },

  methods:{
    addToPlaylist(index){
      this.$emit('add', index);
    }

  },
     
};
</script>

<style scoped>
.even {
    background-color: rgb(231, 127, 231);
}

</style>