<template>
    <div>
        <TopNav />
        <ArticleList />
        <SideNavVue />
        <footerVue />

    </div>
</template>
<style scoped>
    *{
        margin: 0;
        padding: 0;
    }

    
</style>

<script>
import ArticleList from '../components/ArticleList.vue'
import TopNav from '../components/TopNav.vue'
import SideNavVue from '../components/SideNav.vue'
import footerVue from '../components/footer.vue'

export default {
    components:{
        TopNav,
        ArticleList,
        SideNavVue,
        footerVue
    }
}
</script>