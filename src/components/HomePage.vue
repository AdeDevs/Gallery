<template>
    <div class="container">
        <header>
            <h1>This Gallery Was Built By <a href="https://linktr.ee/adedevs">{{ developer }}</a></h1>
        </header>
        <img :src="image" alt="image" />
        <p>{{ museFirst }} {{ museLast }}</p>
        <br>
        <button @click="shuffleNextImage()">Prev</button>
        <button @click="shuffleNextImage()">Next</button>
        <footer>
            <h1>This Gallery Was Built By <a href="https://linktr.ee/adedevs">{{ developer }}</a></h1>
        </footer>
    </div>
</template>

<script>
export default {
    name: "HomePage",
        data() {
            return {
                developer: "AdeDevs",
                image: "https://randomuser.me/api/portraits/men/19.jpg",
                museFirst: "Jon",
                museLast: "Doe"
            }
        },
        methods: {
            async shuffleNextImage() {
                const res = await fetch("https://randomuser.me/api/");
                const { results } = await res.json();
                
                this.museFirst = results[0].name.first;
                this.museLast = results[0].name.last;
                this.image = results[0].picture.large;
            }
        }
    }
</script>

