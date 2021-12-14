<template>
  <div class="ImageGallery">
    <h1>Саня, ты зе бест с ДР!</h1>

    <div class="cube-container">

      <div ref="cube"
           class="cube"
           :class="classList"
           @click="onChange"
      >

        <img
             v-for="(src, index) in list"
             :key="src"
             :src="src"
             class="cube-face-image"
             :class="`image-${index + 1}`"
        />
      </div>

    </div>

    <h2>Это кубик воспоминаний, крути и будь уверен твоя молодость была (<span>и остается</span>) крутой, <span>старикан</span> ты эдакий заъахаха</h2>

    <audio autoplay controls="controls">
      <source src="https://upload.wikimedia.org/wikipedia/commons/f/f5/Good_Morning_to_All.ogg" type="audio/ogg">
    </audio>

  </div>
</template>

<script>
export default {
    name: 'IndexPage',

    data() {
        return {
            list: [],

            library: [
                'https://sun9-80.userapi.com/impf/c841332/v841332698/3ba48/Fat-NM6afEQ.jpg?size=719x960&quality=96&sign=5d54f921a741e6b9ef464968fe720bcd&type=album',
                'https://sun9-77.userapi.com/impf/c840426/v840426854/250cc/KragyQ5idOI.jpg?size=719x960&quality=96&sign=9855d00fc47d40ea4cb193167047b565&type=album',
                'https://sun9-31.userapi.com/impf/c840139/v840139479/43b1f/-3nuuf8XdZg.jpg?size=719x960&quality=96&sign=8640a46edfc1fe2a8e69e88e92ea5864&type=album',
                'https://sun9-13.userapi.com/impf/c845019/v845019800/1511a8/3l_smP1ADbI.jpg?size=960x721&quality=96&sign=0a766daf5bf5206718745da7104e1cc8&type=album',
                'https://sun9-12.userapi.com/impf/c604825/v604825539/354ef/wgCOL8HN2bM.jpg?size=720x960&quality=96&sign=a8dcf46461cbc7bac8ce19478abdc4d9&type=album',
                'https://sun9-69.userapi.com/impf/c846018/v846018285/834ae/lZcxD2_ammw.jpg?size=539x960&quality=96&sign=464b29c22298943e36ec8d2177d84197&type=album',
                'https://sun9-20.userapi.com/impf/c841232/v841232698/3b925/zBWZHZoIsgI.jpg?size=719x960&quality=96&sign=b78d76d8ba3b763bd2fc2abd8b80ce6f&type=album',
                'https://sun9-9.userapi.com/impf/c840635/v840635698/24fdd/ADJPhiTyGWE.jpg?size=719x960&quality=96&sign=d88b1a8efc0f14ee0b0818b53cf7ae50&type=album',
                'https://sun9-63.userapi.com/impf/c841120/v841120219/41926/EvKjx-iq6Y4.jpg?size=720x960&quality=96&sign=6432fb68f87b13e6142d75ca3f5b8eec&type=album',
                'https://sun9-56.userapi.com/impf/c845524/v845524653/df483/t2sLh9GYrlI.jpg?size=960x720&quality=96&sign=8490a96b518b95490ff246b3bd116f57&type=album',
                'https://sun9-62.userapi.com/impf/c849324/v849324786/63300/DeJdpVWtGpw.jpg?size=720x960&quality=96&sign=a4cb215112429541ceb2534ec7bdfe00&type=album',
                'https://sun9-72.userapi.com/impf/c830401/v830401858/15b749/ha_PYNn84AU.jpg?size=539x960&quality=96&sign=228688d18ec971219415cf4fdcac980f&type=album',
                'https://sun9-55.userapi.com/impf/c841629/v841629960/490b9/HAzZN0lfOpc.jpg?size=780x1040&quality=96&sign=e97a8b7be4e50fcc5955693375a31016&type=album',
                'https://sun9-33.userapi.com/impf/c626230/v626230539/6b8b/VXLUgeRV7mc.jpg?size=720x960&quality=96&sign=e4a47adb99ceb37d16bbff30646c38ce&type=album',
                'https://sun9-54.userapi.com/impf/c824602/v824602338/57e42/LDj0ILc-S9c.jpg?size=1080x1920&quality=96&sign=6513724e8b929705acdc3926dd1fb404&type=album',
                'https://sun9-54.userapi.com/impf/c841329/v841329515/669eb/miV2xbA3ltA.jpg?size=571x862&quality=96&sign=27a04f81625094fad835e6bee5b244db&type=album',
                'https://sun9-47.userapi.com/impg/dpu0n7iPD3jNLgGDt7XPnllJw4p95IVUfxQmoQ/kMEfZG8J7x0.jpg?size=1266x1688&quality=96&sign=6b66567801832ed26e374429d8c24fa8&type=album',
                'https://sun9-34.userapi.com/impg/3CiqFHMSkDV-MaZtzeDTGrj4ZGGfW8EboN8wwA/Hkq3fU71ZDs.jpg?size=1440x1920&quality=96&sign=6d5e5a981a946b1c031dcb361fe3e758&type=album',
                'https://sun9-70.userapi.com/impg/gZGZqebpby3w47sb22kN4RDUGXtjC7mQUQboJg/A_bmX8jtDw4.jpg?size=720x960&quality=96&sign=881a65f6c8882f3dc482473c7fc8b20c&type=album',
                'https://sun9-25.userapi.com/impg/9xDOjVG5zVk9o52Vn_kfIigN-Q9WVa95hiRYIA/CuBUHptw8wg.jpg?size=1197x1600&quality=96&sign=16a2b9a4453fb46bf9940485427b35d7&type=album',
                'https://sun9-79.userapi.com/impg/TjIb2dlGTr6tnzAVsblwh03Q3ULxDpEPHnBDaA/WKMwOOsgWZU.jpg?size=1620x2160&quality=96&sign=b5c7e865f8d2887b4f1d1a550e11b37b&type=album',
                'https://sun9-12.userapi.com/impg/6Ks9y0KwJ3GZHxDk0yTXvfUGn2gGw7s4ud9Kew/D7AAo3rB8Jo.jpg?size=1440x1920&quality=96&sign=c23f4fc081d395cc50d5f2fc49b7afd1&type=album',
                'https://sun9-30.userapi.com/impg/SAvbKbpXivvNgRDGMu12v1mVoJmOtSzoCSYynQ/1vp6XpJYW1Q.jpg?size=1200x1600&quality=96&sign=e867cbbbf9382483265d1df062e46d40&type=album',
                'https://sun9-27.userapi.com/impf/c830108/v830108709/152e16/0e8IegNvfSo.jpg?size=720x960&quality=96&sign=742fb4425491e935b077d1a0a75c0292&type=album',
                'https://sun9-75.userapi.com/impf/c824600/v824600476/3953e/_UKKiQR9Us4.jpg?size=960x720&quality=96&sign=ab8f013a1f4552b798befb84073d3fc8&type=album',
            ],

            activeIndex: null,
            index: -1,
        }
    },

    computed: {
        classList() {
            return {
                'initial-position': this.activeIndex === null,
                [`show-image-${this.activeIndex}`]: this.activeIndex !== null,
            };
        }
    },

    mounted() {
        this.getList(0);
    },

    methods: {
        onChange() {
            this.index++;
            this.activeIndex++;

            if (this.index % 6 === 0) {
                this.activeIndex = 0;
                this.getList();
            }
        },

        getList(i = this.index) {
            if (this.index + 6 <= this.library.length) {
                this.list = this.library.slice(i, i + 6);
            } else {
                this.index = 0;
                this.getList();
            }
        },
    }
}
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Montserrat:500);

.ImageGallery {
  text-align: center;
}

:root {
  /* Base font size */
  font-size: 10px;

  /* Border color variable */
  --border-color: #ff4c30;
}

* {
  box-sizing: border-box;
}

body {
  font-family: "Montserrat", Arial, sans-serif;
  text-align: center;
  color: #fafafa;
  background-color: #080808;
}

h1 {
  font-size: 4rem;
}

h2 span {
    background-image: linear-gradient(to left, violet, indigo, blue, green, yellow, orange, red);
    color: black;
}

h2 {
    max-width: 400px;
    text-align: center;
    margin: 0 auto 2.5rem;
  font-size: 2rem;
}

.cube-container {
  position: relative;
  width: 30rem;
  height: 30rem;
  margin: 5rem auto 6rem;
  perspective: 100rem;
}

.cube {
  position: absolute;
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
  transition: transform 1s cubic-bezier(0.32, 0.05, 0.35, 1.6);
}

.cube-face-image {
  width: 300px;
  height: 300px;
  display: block;
  position: absolute;
  /* opacity: 0.95; */
  /* border: 0.2rem solid #fafafa; */
  box-shadow: 0 0 0.5rem #fff,
  0 0 1.5rem var(--border-color),
  0 0 3rem var(--border-color);
  object-fit: cover;
}

.image-buttons {
  display: grid;
  grid-template-columns: repeat(3, auto);
  grid-gap: 1.5rem;
  justify-content: center;
}

.image-buttons input {
  border: 0.2rem solid #fafafa;
}

.image-buttons input:focus {
  outline: none;
  border: 0.2rem solid var(--border-color);
}

/* Transform images to create cube */

.image-1 {
  transform: translateZ(15rem);
}

.image-2 {
  transform: rotateX(-180deg) translateZ(15rem);
}

.image-3 {
  transform: rotateY(90deg) translateZ(15rem);
}

.image-4 {
  transform: rotateY(-90deg) translateZ(15rem);
}

.image-5 {
  transform: rotateX(90deg) translateZ(15rem);
}

.image-6 {
  transform: rotateX(-90deg) translateZ(15rem);
}

/* Transform cube to show correct image */

.cube.initial-position {
  transform: translateZ(-15rem) translateY(-2rem) rotateX(-15deg) rotateY(18deg) rotateZ(2deg);
}

input {
  width: 100px;
  height: 100px;
  object-fit: cover;
}

.cube.show-image-1 {
  transform: translateZ(-15rem);
}

.cube.show-image-2 {
  transform: translateZ(-15rem) rotateX(180deg);
}

.cube.show-image-3 {
  transform: translateZ(-15rem) rotateY(-90deg);
}

.cube.show-image-4 {
  transform: translateZ(-15rem) rotateY(90deg);
}

.cube.show-image-5 {
  transform: translateZ(-15rem) rotateX(-90deg);
}

.cube.show-image-6 {
  transform: translateZ(-15rem) rotateX(90deg);
}
</style>
