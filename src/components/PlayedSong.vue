<template>
    <div id="display">        
        <i>{{ title }}</i>
        <p>{{ artist }}</p>
        <button v-on:click="removeFromPlayList" id="button">Remove From Playlist</button>        
    </div>
</template>

<script>
export default {
    name: 'PlayedSong',
    props: {
        title: {
            type: String,
            required: true
        },
        artist : {
            type: String
        }       
    },
    methods: {
        removeFromPlayList: function() {
             this.$emit('removeEvent', this.title, this.artist);
        }
    }
}
</script>

<style scoped>
#display {
        width: 18vw;
        height: 20vh;
        padding-top: 35px;
        margin: 10px;
        border: 1px solid grey;
}
#button {
    color: white;
    background: purple;
    padding: 10px;
}
</style>