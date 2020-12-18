
<template>
   <div>
      
       <play-list :songs="playlistSongs" @remove="addToSonglist"></play-list>
       <song-list :songs="songs" @add="addToPlaylist"></song-list>
   </div>
</template>


<script>

import PlayList from './PlayList.vue';
import SongList from './SongList.vue';
export default {
    name: 'PageBody',
    components: {
        PlayList,
        SongList,
    },
    data () {
        return {
            playlistSongs: [],
            songs: [
                {
                    title: 'Perfact',
                    artist: 'Ed Sheeran',
                },
                {
                    title: 'Sorry',
                    artist: 'Justin Biber',
                   
                },
                {
                    title: 'Senorita',
                    artist: 'Shawn Mendus',
                    
                },
                {
                    title: 'Trouble',
                    artist: 'Taylor Swift',
                   
                },
                {
                    title: 'With You',
                    artist: 'Tyler Shaw',
                    
                }
            ]
        }
    },
    methods: {
       addToPlaylist(index){
           let song = this.songs.splice(index, 1)[0];
           this.playlistSongs.splice(0, 0, song);

       },
       addToSonglist(index){
           let song = this.playlistSongs.splice(index, 1)[0];
           this.songs.splice(0, 0, song);
       },

    }
    
}
</script>


<style scoped>

</style>