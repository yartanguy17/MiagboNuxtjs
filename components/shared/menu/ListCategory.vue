<template>
    <li class=" menu-item-has-children dropdown">
        <nuxt-link :to="localePath(menuData.url)">
            {{ menuData.text }}
        </nuxt-link>
        <ul v-if="nom != null" class="sub-menu">
            <ListCategory
                v-for="item of menuData.subMenu"
                :menu-data="item"
                :key="item.text"
            />
        </ul>
    </li>
</template>

<script>
export default {
    name: 'ListCategory',
    props: {
       nom: String
    },
    data: () => {
        return {};
    }
};
</script>