<template>
    <div id="songlistDisplay"> 
        <Song v-for="item in list" :key="item.title" :artist="item.artist" :title="item.title" @myEvent="myHandleEvent"/>
    </div>
</template>

<script>
import Song from './Song.vue'

export default {
    name: 'SongList',
    props: {
        list: {
            type: Array,
            required: true
        }
    },
    components: {
        Song
    },
    methods: {
        myHandleEvent: function(emitTitle, emitArtist) {
            this.$emit('myRemoveEvent', emitTitle, emitArtist);
            // this.$emit('myAddEvent', emitTitle, emitArtist);
        }
    }
    
}
</script>
<style scoped>
    #songlistDisplay {
        display: float;
    }
</style>