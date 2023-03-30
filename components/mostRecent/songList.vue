<template>
  <div class="px-4 md:px-24">
    <div class="flex flex-col md:flex-row w-full h-3/6">
      <!-- Columna de la imagen y botones -->
      <div
        class="
          w-full
          md:w-1/2
          flex flex-col
          justify-center
          items-center
          px-8
          pt-8
          rounded-lg
        "
      >
        <img
          :src="currentImg"
          alt="Canción"
          class="w-96 h-96 object-cover rounded-md mb-8 shadow-lg"
        />

        <div class="flex justify-start rounded-lg p-4 pl-0">
          <img
            src="../../static/assets/play.png"
            class="
              p-3
              cursor-pointer
              transition-colors
              rounded-lg
              duration-300
              hover:bg-gray-200 hover:bg-opacity-25
            "
            alt=""
            @click="playAudio()"
          />

          <img
            src="../../static/assets/pause.png"
            class="
              p-3
              rounded-lg
              cursor-pointer
              transition-colors
              duration-300
              hover:bg-gray-200 hover:bg-opacity-25
            "
            alt=""
            @click="pauseAudio()"
          />
        </div>

        <audio
          ref="audio"
          id="audio"
          :src="currentTrack"
          preload="auto"
        ></audio>
      </div>
      <!-- Columna de la lista de canciones -->
      <div
        class="w-full bg-primary-opaco-dark rounded-lg text-white md:w-1/2 p-8"
      >
        <h2 class="text-3xl font-bold mb-4 title">Canciones</h2>
        <div style="height: 500px; overflow-y: scroll">
          <ul>
            <li
              v-for="(track, index) in trackList"
              :key="index"
              class="
                flex
                items-center
                mb-4
                cursor-pointer
                transition-colors
                duration-300
                hover:bg-gray-200 hover:bg-opacity-25
              "
              @click="changeTrack(track)"
            >
              <img :src="track.img" class="w-12 h-12 rounded mr-4" />
              <span class="itemList">{{ track.name }}</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SongList",

  data() {
    return {
      currentTrack: null,
      currentImg: null,
      trackList: [
        {
          img: "/music/img/EuropeCarrie.jpg",
          src: "/music/001Europe-Carrie.mp3",
          name: "Europe - Carrie",
        },
        {
          img: "/music/img/TotoAfrica.jpg",
          src: "/music/002 Toto - Africa.mp3",
          name: "Toto - Africa",
        },

        {
          img: "/music/img/Phill Collins - Another Day In Paradise.jpg",
          src: "/music/003 Phill Collins - Another Day In Paradise.mp3",
          name: "Phill Collins - Another Day In Paradise",
        },
        {
          img: "/music/img/Billy Joel - Honesty.jpg",
          src: "/music/004 Billy Joel - Honesty.mp3",
          name: "Billy Joel - Honesty",
        },
        {
          img: "/music/img/EuropeCarrie.jpg",
          src: "/music/001Europe-Carrie.mp3",
          name: "Europe - Carrie",
        },
        {
          img: "/music/img/TotoAfrica.jpg",
          src: "/music/002 Toto - Africa.mp3",
          name: "Toto - Africa",
        },

        {
          img: "/music/img/Phill Collins - Another Day In Paradise.jpg",
          src: "/music/003 Phill Collins - Another Day In Paradise.mp3",
          name: "Phill Collins - Another Day In Paradise",
        },
        {
          img: "/music/img/Billy Joel - Honesty.jpg",
          src: "/music/004 Billy Joel - Honesty.mp3",
          name: "Billy Joel - Honesty",
        },
        {
          img: "/music/img/EuropeCarrie.jpg",
          src: "/music/001Europe-Carrie.mp3",
          name: "Europe - Carrie",
        },
        {
          img: "/music/img/TotoAfrica.jpg",
          src: "/music/002 Toto - Africa.mp3",
          name: "Toto - Africa",
        },

        {
          img: "/music/img/Phill Collins - Another Day In Paradise.jpg",
          src: "/music/003 Phill Collins - Another Day In Paradise.mp3",
          name: "Phill Collins - Another Day In Paradise",
        },
        {
          img: "/music/img/Billy Joel - Honesty.jpg",
          src: "/music/004 Billy Joel - Honesty.mp3",
          name: "Billy Joel - Honesty",
        },
        {
          img: "/music/img/EuropeCarrie.jpg",
          src: "/music/001Europe-Carrie.mp3",
          name: "Europe - Carrie",
        },
        {
          img: "/music/img/TotoAfrica.jpg",
          src: "/music/002 Toto - Africa.mp3",
          name: "Toto - Africa",
        },

        {
          img: "/music/img/Phill Collins - Another Day In Paradise.jpg",
          src: "/music/003 Phill Collins - Another Day In Paradise.mp3",
          name: "Phill Collins - Another Day In Paradise",
        },
        {
          img: "/music/img/Billy Joel - Honesty.jpg",
          src: "/music/004 Billy Joel - Honesty.mp3",
          name: "Billy Joel - Honesty",
        },
      ],
      audio: null,
    };
  },
  mounted() {
    this.audio = this.$refs.audio;
    this.currentTrack = this.trackList[0].src;
    this.currentImg = this.trackList[0].img;
  },

  methods: {
    playAudio() {
      this.audio.play();
    },
    pauseAudio() {
      this.audio.pause();
    },
    async changeTrack(track) {
      this.currentTrack = track.src;
      this.currentImg = track.img;
      this.audio.src = this.currentTrack;
      await this.audio.load();
      this.audio.play();
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&family=Simonetta&display=swap");
.title {
  font-family: "Simonetta", cursive;
  font-weight: 100;
}
.itemList {
  font-family: "PT Sans Caption", sans-serif;
}
</style>
