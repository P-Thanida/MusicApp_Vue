<template>
  <div id="app">
    <header>
      <h1>My Music</h1>
    </header>
    <main>
      <section class="player">
        <h2 class="song-title">
          {{ current.title }} - <span>{{ current.artist }}</span>
        </h2>
        <span>
          <div class="controls">
            <button class="prev">Prev</button>
            <button class="play">Play</button>
            <button class="pause">Pause</button>
            <button class="next">Next</button>
          </div>
        </span>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      current: {},
      index: 0,
      isPlaying: false,
      songs: [
        {
          title: 'Jak kan duai dee',
          artist: 'Tilly Birds',
          src: require('./assets/s1.mp3'),
        },
        {
          title: 'Dai tae nuk tung',
          artist: 'Only Monday',
          src: require('./assets/s2.mp3'),
        },
      ],
      player: new Audio(),
    };
  },
  created() {
    this.current = this.songs[this.index];
    this.player.src = this.current.src;
    // this.player.play();
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
}

header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 15px;
  background-color: #212121;
  color: #fff;
}
</style>
