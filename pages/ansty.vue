<template>
    <section class="AnstyPage">
        <div class="wrapper">

            <div v-for="i in list"
                 :key="i.title"
                 class="item"
            >
                <div class="polaroid"><img :src="i.src"/>
                    <div class="caption">{{ i.title }}</div>
                </div>
            </div>

        </div>
    </section>
</template>

<script>
export default {
  name: "AnstyPage",

    data() {
        return {
            list: [
                {
                    src: 'https://sun9-31.userapi.com/impg/kxFU1LErsVrSfyPD-vfqqzJ-WlJd2FMNC1KhPg/anWKOS8CZ1Q.jpg?size=960x721&quality=96&sign=4c7ec05672076d4b4bfcd492c4b313be&type=album',
                    title: 'С днем рождения!',
                },
                {
                    src: 'https://sun9-62.userapi.com/impf/c854228/v854228344/51c79/htgOC_RQvgk.jpg?size=959x721&quality=96&sign=ea2cf8eaa70d25cc3dee68983cd98d7c&type=album',
                    title: 'Хочу пожелать тебе всего самого наилучшего',
                },
                {
                    src: 'https://sun9-2.userapi.com/impg/NrMRQv7l1DnMfJj5FU-6cYUGKGdO5439Y3mf7g/RvyT1Qg3540.jpg?size=1020x580&quality=96&sign=70c32f14b9490669fd0a7de29afecd5e&type=album',
                    title: 'Пускай все, что ты планируешь, у тебя будет в ближайшее время',
                },
                {
                    src: 'https://sun9-49.userapi.com/impg/8w-bolWVkhe9cpiTEIvSSTaOCvhIfj_RGJ85Og/wROv4KGnvmM.jpg?size=768x1024&quality=96&sign=938af9f2c0719e5552b9aa9ebaacd629&type=album',
                    title: 'Будь собой и следуй за мечтой',
                },
            ]
        }
    },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');

* {
    box-sizing: border-box;
}
body {
    font-family: 'Pacifico', cursive;
    line-height: 1.618em;
    background-color: #e4d4bb;
    background-image: repeating-radial-gradient(circle,
    #E4D4BB, #E7DAC6 50%, #E7DAC6 100%
    );
    background-size: 10px 10px;
}
img {
    max-width: 100%;
    height: auto;
}
.wrapper {
    width: 100%;
    padding: 0 2rem;
    text-align: center;
}
.polaroid {
    background: #fff;
    padding: 1rem;
    box-shadow: 0 0.25rem 1rem rgba(0,0,0,0.2);
}
.caption {
    font-size: 1.125rem;
    text-align: center;
    line-height: 2em;
}
.item {
    display: inline-block;
    margin-top: 2rem;
}
.item .polaroid:before {
    content: '';
    position: absolute;
    z-index: -1;
    transition: all 0.35s;
}
.item:nth-of-type(4n+1) {
    transform: scale(0.8, 0.8) rotate(5deg);
    transition: all 0.35s;
}
.item:nth-of-type(4n+1) .polaroid:before {
    transform: rotate(6deg);
    height: 20%;
    width: 47%;
    bottom: 30px;
    right: 12px;
    box-shadow: 0 2.1rem 2rem rgba(0,0,0,0.4);
}
.item:nth-of-type(4n+2) {
    transform: scale(0.8, 0.8) rotate(-5deg);
    transition: all 0.35s;
}
.item:nth-of-type(4n+2) .polaroid:before {
    transform: rotate(-6deg);
    height: 20%;
    width: 47%;
    bottom: 30px;
    left: 12px;
    box-shadow: 0 2.1rem 2rem rgba(0,0,0,0.4);
}
.item:nth-of-type(4n+4) {
    transform: scale(0.8, 0.8) rotate(3deg);
    transition: all 0.35s;
}
.item:nth-of-type(4n+4) .polaroid:before {
    transform: rotate(4deg);
    height: 20%;
    width: 47%;
    bottom: 30px;
    right: 12px;
    box-shadow: 0 2.1rem 2rem rgba(0,0,0,0.3);
}
.item:nth-of-type(4n+3) {
    transform: scale(0.8, 0.8) rotate(-3deg);
    transition: all 0.35s;
}
.item:nth-of-type(4n+3) .polaroid:before {
    transform: rotate(-4deg);
    height: 20%;
    width: 47%;
    bottom: 30px;
    left: 12px;
    box-shadow: 0 2.1rem 2rem rgba(0,0,0,0.3);
}
.item:hover {
    filter: none;
    transform: scale(1, 1) rotate(0deg) !important;
    transition: all 0.35s;
}
.item:hover .polaroid:before {
    content: '';
    position: absolute;
    z-index: -1;
    transform: rotate(0deg);
    height: 90%;
    width: 90%;
    bottom: 0%;
    right: 5%;
    box-shadow: 0 1rem 3rem rgba(0,0,0,0.2);
    transition: all 0.35s;
}
</style>
