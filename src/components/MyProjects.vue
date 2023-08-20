<template>
    <section class="my-proj" id="my-proj" ref="myProj">
        <section class="tuneify">
            <h1 :class="{ 'scroll-up': isInViewport }">Featured <span>Projects</span></h1>
            <a href="https://tuneify.onrender.com/" target="_blank">
                <div :class="{ 'scroll-up': isInViewport }" class="tuneify-img">
                    <img src="../assets/imgs/tuneify1.jpg" alt="">
                    <a href="https://github.com/LidorLevi123/tuneify-frontend" target="_blank">Code - FE</a>
                    <a href="https://github.com/LidorLevi123/tuneify-backend" class="code" target="_blank">Code - BE</a>
                </div>
                <h2 :class="{ 'scroll-up': isInViewport }" class="hover-underline">Tuneify - a Spotify mockup</h2>
            </a>
            <p :class="{ 'scroll-up': isInViewport }">With two of my friends Lidor Levi and Nitzan Peer, I have brought a
                dynamic Spotify mockup to life
                using Vue.js.
                Melding design prowess, frontend expertise, and coding finesse, our creation offers an immersive user
                experience
                akin to the actual platform. Whether you're diving into handpicked playlists, exploring new Genres, or
                enjoying beloved tracks, our Vue-powered mockup embodies the essence of musical exploration. This project
                stands
                as a testament to our shared dedication to innovation and a profound affinity for the world of music.</p>
        </section>
        <section class="first-proj">

            <div class="mine" :class="{ 'scroll-up': isInViewport }">
                <a href="https://ron5054.github.io/Minesweeper/" target="_blank">
                    <img src="../assets/imgs/minesweeper.jpg" alt="">
                    <a href="https://github.com/ron5054/Minesweeper" target="_blank">Code</a>
                    <h1>Minesweeper</h1>
                </a>
                <p>My first game written in JS after only 3 weeks of programming training</p>
            </div>
            <div class="meme" :class="{ 'scroll-up': isInViewport }">
                <a href="https://ron5054.github.io/Meme-Generator/" target="_blank">
                    <img src="../assets/imgs/meme.jpg" alt="">
                    <a href="https://github.com/ron5054/Meme-Generator" target="_blank">Code</a>
                    <h1>Meme-Generator</h1>
                </a>
                <p>This project demonstraits the power of HTML Canvas</p>
            </div>
        </section>
        <section class="gmail" :class="{ 'scroll-up': isInViewport }">
            <a href="https://ron5054.github.io/AppSus/#/mail" target="_blank">
                <img src="../assets/imgs/gmail.jpg" alt="">
                <a href="https://github.com/ron5054/AppSus" target="_blank">Code</a>
                <h1>Gmail mockup</h1>
            </a>
            <p>A Gmail mockup i have created after 4 days learning Vue.js Framework.</p>
        </section>
    </section>
</template>
  
<script>
export default {
    data() {
        return {
            isInViewport: false
        }
    },
    mounted() {
        const options = {
            root: null,
            rootMargin: "0px",
            threshold: 0.2,
        };
        this.observer = new IntersectionObserver(this.handleIntersection, options)
        this.observer.observe(this.$refs.myProj)
    },
    methods: {
        handleIntersection(entries) {
            this.isInViewport = entries[0].isIntersecting
        },
    },
    beforeUnmount() {
        if (this.observer) {
            this.observer.disconnect()
        }
    },
};
</script>

  
