<template>
    <v-container>
        <v-btn route to="/News">Retour</v-btn>
            <span v-for="(val , propriete) in obj" :key="propriete">
                <span v-if="propriete == index">
                    <v-row class="my-4">
                        <v-col xl="6" lg="6" md="12">
                            <div>
                                <v-img width="100%" class="sary" :src="val.image"></v-img>
                                <v-row>
                                    <v-col>
                                        <img width="100%" class="sary" :src="val.img1"/>
                                    </v-col>
                                    <v-col>
                                        <img width="100%" class="sary" :src="val.img2"/>
                                    </v-col>
                                    <v-col>
                                        <img width="100%" class="sary" :src="val.img3"/>
                                    </v-col>
                                </v-row>
                            </div>
                        </v-col>
                        <v-col cols="6" xl="6" lg="6" md="12" sm="12" xs="12">
                            <Listegg v-bind:titre="val.titre" v-bind:description="val.description" v-bind:prix="val.prix">
                            </Listegg>
                        </v-col>
                    </v-row>
                </span>
            </span>
        <!--
        <div @click="refresh">
            <span v-show="index > 1">
                <router-link :to="`/Product/${parseInt(index)-1}`">Précédent</router-link>
            </span>
        </div>
        <div @click="refresh">
            <router-link :to="`/Product/${parseInt(index)+1}`">Suivant</router-link>
            <router-link :to="next">Suivant</router-link>
        </div>
        -->
    </v-container>
</template>
<script>
import json from './../data/news.json'
import Listegg from './../components/Listegg'

export default {
    name: 'Product',
    components: {
        Listegg,
    },
    data(){
        return{
            obj : json,
            index : this.$route.params.numero,
        }
    },/*
    computed: {
        next: function(){
            return '/Product/' + (parseInt(this.index) + 1);
        }
    },
    methods: {
        refresh() {
            return location.reload();
            //this.$forceUpdate();
        }
    }*/
}
</script>
<style scoped>
.sary{
    box-shadow: 0px 3px 10px grey;
}
</style>