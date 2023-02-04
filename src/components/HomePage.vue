<template>
    <div>
        <h1>My Gallery HomePage Was Built By {{ developer }}</h1>
        <img :src="image" alt="image" />
        <br>
        <button @click="shuffleNextImage()">Next</button>
    </div>
</template>

<script>
export default {
    name: "HomePage",
        data() {
            return {
                developer: "Adeyemi",
                image: "https://randomuser.me/api/portraits/men/19.jpg",
            }
        },
        methods: {
            async shuffleNextImage() {
                const res = await fetch("https://randomuser.me/api/");
                const { results } = await res.json();
                
                this.developer = 'Reece James';
                this.image = results[0].picture.large
            }
        }
    }
</script>

