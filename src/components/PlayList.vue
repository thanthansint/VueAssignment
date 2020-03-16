<template>
    <div id="playlistDisplay">        
        <PlayedSong v-for="item in list" :key="item.title" :artist="item.artist" :title="item.title" @removeEvent="handleRemoveEvent"/>
    </div>
</template>

<script>
import PlayedSong from './PlayedSong.vue'


export default {
    name: 'PlayList',
    components: {
        PlayedSong
    },
    props: {
        list: {
            type: Array,
            required: true
        }
    },
    methods: {
        handleRemoveEvent: function(emitTitle, emitArtist) {
            this.$emit('mySubEvent', emitTitle, emitArtist);
        }
    }
}
</script>
<style scoped>
#playlistDisplay {
        display: float;
    }
</style>