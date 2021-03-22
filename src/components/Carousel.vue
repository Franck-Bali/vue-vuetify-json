<template>
    <v-carousel cycle show-arrows-on-hover height="93vh">
        <v-carousel-item v-for="(liste,k) in listes" :key="k" :src="liste.src">
            <div class="citation">
                <h1>{{liste.txt}}</h1>
            </div>
        </v-carousel-item>
    </v-carousel>
</template>
<script>
    export default {
        name: 'Carousel',
        data: () => ({
            listes: [
                {txt: "L'élégence est la seule beauté qui fane jamais", src: require('@/assets/carousel/carousel (1).jpg')},
                {txt: "La simplicité est la clé de toute véritable élégance", src: require('@/assets/carousel/carousel (2).jpeg')},
                {txt: "La mode passe, le style reste", src: require('@/assets/carousel/carou.jpg')},
            ],
        }),
    }
</script>
<style scoped>
.citation{
    text-align: center;
    position: relative;
    top: 40vh;
    text-shadow: 0px 0px 15px grey;
}
.citation::after{
    content:"";
    position: absolute;
    width: 4vw;
    height: 5px;
    background: red;
    left: 48vw;
    right: 48vw;
}
</style>
