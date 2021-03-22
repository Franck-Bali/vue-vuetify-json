<template>
    <div class="news">
        <div class="header" v-bind:style="{backgroundImage: 'url('+bg+')'}">
            <h2>Nouveautés</h2>
        </div>
        <v-container>
            <v-row class="mt-4">
                <v-col xl="3" lg="4" md="6" sm="12" v-for="(val , propriete) in obj" v-bind:key="propriete">
                    <v-card>
                        <v-img :src="val.image"></v-img>
                        <v-card-text class="my-3" style="text-align:center;">
                            <h3>{{val.titre}}</h3>
                        </v-card-text>
                        <v-divider></v-divider>
                        <v-card-actions>
                            <v-btn text color="red" route :to="`/Product/${propriete}`">
                                <h2>{{val.prix}} $</h2>
                            </v-btn>
                            <v-spacer></v-spacer>
                            <v-btn class="m-2" dark small fab depressed color="yellow accent-3" route :to="`/Product/${propriete}`">
                                    <v-icon dark>
                                        mdi-chevron-right
                                    </v-icon>
                            </v-btn>
                        </v-card-actions>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>
<script>
import json from './../data/news.json'
export default {
    name: 'News',
    /*data: () => ({
    }),*/
    data(){
        return{
            obj : json,
            bg : "bg/aaa.jpg",
        }
    }
}
</script>
<style scoped>
.header{
    height: 60vh;
    padding-top: 28vh;
    text-align: center;
    color: black;
    font-size:23px;
    font-weight: black;
}
.header h2::before{
    content: "Nouveautés";
    position: absolute;
    transform: scale(1.75);
    color: rgba(255,0,0,0.3);
}
router-link{
    color: red;
}
</style>