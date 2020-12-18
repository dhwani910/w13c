<template>
    <div>
        <h1>Play List !</h1>
        <p v-for="(song, index) in songs" :key="index" @click="removeFromPlaylist(index)">
            {{song.artist}} - {{song.title}}
        </p>
        

    </div>
</template>


<script>
export default {
    name: 'PlayList',
    props: {
        songs: Array
    },
    methods: {
        removeFromPlaylist(index){
            this.$emit('remove', index);
        }
    }
}
</script>

<style scoped>

</style>