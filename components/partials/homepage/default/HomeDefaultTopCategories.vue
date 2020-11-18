<template lang="html">
    <div class="ps-top-categories" v-if="!$fetchState.pending">
        <div class="ps-container">
            <h3>{{ $t('autopart.topCategories') }}</h3>
            <div class="row">
                <div class="col-xl-2 col-lg-3 col-md-4 col-sm-4 col-6 " v-for="category of categories" :key="category.uid">
                    <div class="ps-block--category">
                        <nuxt-link :to="`/shop/${category.uid}`">
                            <a class="ps-block__overlay"></a>
                        </nuxt-link>                        
                        <img
                            :src="baseUrl + category.img"
                            alt="martfury"
                        />
                        <p>{{category.nom}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HomeDefaultTopCategories',
    data(){
        return{
            baseUrl: 'http://51.89.97.33:5500',
            categories: [],
        }
    },
    async fetch(){
        this.categories = await fetch('http://51.89.97.33:5500/api/categories')
            .then(res => res.json());
    }
};

</script>

<style lang="scss" scoped></style>
