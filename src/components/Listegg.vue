<template>
    <div>
        <h1>{{this.titre}}</h1>
        <p>{{this.description}}</p>
        <h4>{{this.prix}}</h4>
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
}
</script>
<style scoped>
</style>