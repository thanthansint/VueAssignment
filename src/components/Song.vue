<template>
    <div id="display">    
        <i>{{ title }}</i>
        <p>{{ artist }}</p>
        <button v-on:click="changeToPlayList" id="button">Add to Playlist</button>
    </div>
</template>
<script>
export default {
    name: 'Song',
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
        changeToPlayList: function() {
             this.$emit('myEvent', this.title, this.artist);
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