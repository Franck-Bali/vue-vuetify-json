<template>
    <v-carousel cycle show-arrows-on-hover height="93vh">
      <v-carousel-item v-for="(liste,i) in listes" :key="i" :src="liste.src">
      </v-carousel-item>
    </v-carousel>
</template>
<script>
    export default {
        name: 'Carousel',
        data: () => ({
            listes: [
                {src: require('@/assets/carousel/carousel (1).jpg')},
                {src: require('@/assets/carousel/carousel (2).jpeg')},
                {src: require('@/assets/carousel/carou.jpg')},
            ],
        }),
    }
</script>