<template >
    <div class="ps-top-categories" v-if="!$fetchState.pending">
        <div class="ps-container">
            <h3>Nos Produits</h3>
            <div class="row">
                <div class="col-xl-2 col-lg-3 col-md-4 col-sm-4 col-6 " v-for="produit of produits" :key="produit.uid">
                    <div class="ps-block--category">
                        <nuxt-link :to="`/product/${produit.uid}`">
                            <a class="ps-block__overlay"></a>
                        </nuxt-link>                        
                        <img
                            :src="baseUrl + produit.images"
                            :alt="produit.nom"
                            style="height:200px; width:500px"
                        />
                        <p>{{produit.nom}}</p>
                        <p style="color:red">{{produit.prix}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Produits",
    data(){
        return{
            baseUrl: "http://51.89.97.33:5500",
            produits: [],
        }
    },
    async fetch(){
        this.produits = await fetch("http://51.89.97.33:5500/api/products")
            .then(res => res.json())
            .then(res => res.splice(0, 20));
    }
}
</script>

<style lang="scss" scoped>

</style>