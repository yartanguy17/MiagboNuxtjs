<template >
    <ul class="menu--dropdown">
        <template v-for="item of listCategory">
          
            <li :key="item.uid">
                <nuxt-link :to="localePath(item.img)">
                    {{ item.nom }}
                </nuxt-link>
            </li>
        </template>
    </ul>
</template>

<script>
import MenuDefault from '~/components/shared/menu/MenuDefault';
import MenuDropdown from '~/components/shared/menu/MenuDropdown';
import MenuMega from '~/components/shared/menu/MenuMega';


export default {
    name: 'MenuCategories',
    components: { MenuMega, MenuDropdown, MenuDefault },
    data() {
        return {

            listCategory:[],
           
        };
    },
    async fetch(){
        this.listCategory = await fetch('http://51.89.97.33:5500/api/categories')
            .then(res => res.json());
    }
};
</script>

<style lang="scss" scoped></style>
