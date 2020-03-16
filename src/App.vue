<template>
  <div id="app"> 
    <div id="col">
      <p id="textSetting"><strong>Songs List</strong></p>
      <SongList v-bind:list="songlist" @myRemoveEvent="removeSong"/>    
    </div>
    <div id="col">  
      <p id="textSetting"><strong>Played-Songs List</strong></p> 
      <PlayList v-bind:list="playlist" @mySubEvent="addSong"/>
    </div>
  </div>   
</template>

<script>
import SongList from './components/SongList.vue'
import PlayList from './components/PlayList.vue'

export default {
  name: 'App',
  components: {    
    SongList,
    PlayList
  },
  data: function() {
    return {     
      songlist : [
         {
              title: "AAA",
              artist: "Than"
         },
        {
              title: "BBB",
              artist: "Sint"
          },
          {
              title: "CCC",
              artist: "Nyan"
          }
      ],
      playlist: []
    }
  },
  methods: {
    removeSong: function (songTitle, songArtist) {      
      var index = this.songlist.findIndex(obj => obj.title==songTitle && obj.artist == songArtist);     
      this.songlist.splice(index, 1);     
      this.playlist.push({title: songTitle, artist: songArtist});      
    },
    addSong: function (songTitle, songArtist) {
      var index1 = this.playlist.findIndex(obj => obj.title==songTitle && obj.artist == songArtist);     
      this.playlist.splice(index1, 1);     
      this.songlist.push({title: songTitle, artist: songArtist});
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
#col {
  float: left;
  width: 50%;  
  }
#textSetting {
  text-align: left;
  margin-left: 3vw;
  }
</style>
