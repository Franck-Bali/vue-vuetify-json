<template>
    <div>
        <h1>{{this.titre}}</h1>
        <u>
            <h2 class="mt-4">
                Description :
            </h2>
        </u>
        <p>{{this.description}}</p>

        <u>
            <h2 class="mt-4">
                Prix :
            </h2>
        </u>
        <h4>{{this.prix}} $</h4>
        <!--v-btn v-show="nombre > 1" @click="nombre--">-</v-btn-->
        <div class="mt-4">
            <u>
                <h2 class="mt-4">
                    Quantités :
                </h2>
            </u>
            <v-btn :disabled="nombre > 1 ? false : true" @click="nombre--">
                -
            </v-btn>
            <input type="number" v-model="nombre" min="1" max="10"/>
            <v-btn :disabled="nombre < 10 ? false : true" @click="nombre++">
                +
            </v-btn>
        </div>
        <div class="mt-4" style="text-align:center;">
            <v-btn block color="red accent-3" dark @click="achat(titre,nombre,prix)">Acheter</v-btn>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Listegg',
    props: {
        titre: String,
        description: String,
        prix: Number
    },
    data(){
        return{
            nombre: 1,
        }
    },
    methods:{
        achat: function(t,n,p){
            return alert("achat de "+t+" nombre: "+n+", pour : "+p+" . Total : "+(p*n)+"$");
        }
    }
}
</script>
<style scoped>
</style>
