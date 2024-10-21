<template>
    <div>
        <TopNav />
        <SideNavVue />
        <button @click ="goBack"> 返回列表</button>
        <div class="content" v-if="article">
            <h1 contenteditable="true" @input="updateTitle($event)"  >{{article.title}}</h1>
            <p contenteditable="true" @input="updateContent($event)"> {{article.content}}</p>
        </div>
        <div v-else>
            <p> 文章已不存在 </p>
        </div>
        
        <footerVue />
    </div>
    
        
</template>
<style scoped>
    *{
        margin: 0;
        padding: 0;
    }
    .edit{
        margin:  1rem;
    }
    .content{
        height: 100vh;
        text-align: center;
    }
    .content p {
        width: 25 rem;
        padding: 1rem;
    }
</style>
<script>
import TopNav from '../components/TopNav.vue'
import SideNavVue from '../components/SideNav.vue'
import footerVue from '../components/footer.vue'
export default {
    components:{
        TopNav,
        SideNavVue,
        footerVue
    },
    data(){
        return {
            articles:[
                {id:1,title:'热点！现在不仅人民币贬值，人民也贬值',content:'在2024年秋招中，不少学生找不到工作。更有学生签了三方，企业毁约而丧失应届生身份的'},
                {id:2,title:'这个世界不是牛马，就是鸡鸭',content:'草原牛马与城市牛马相见，鸡鸭在微信相见'},
                {id:3,title:'读书是为了什么？',content:'是为了找到更好的工作，还是说面对选择工作时能有更多种选择'},

                ]
        }
    },
    created(){
        const articleId = parseInt(this.$route.params.id); //获取URL中的ID参数
        this.article = this.articles.find(article =>article.id === articleId)
    },
    
    methods:{
        goBack(){
            this.$router.push('/article')
        },
        updateTitle(event){
            this.article.title = event.target.innerText
        },
        updateContent(event){
            
        }
    }
}
</script>