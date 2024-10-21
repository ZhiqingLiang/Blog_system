<template>
    <div class="title">
        <button class="edit"> 编辑 </button>
        <h1>文章列表</h1>
        <div v-for="article in articles" :key="article.id" class="list">
            <!-- articlelist是父组件，articleItem是子组件 -->
            <div class="wholeList"  @click="goToDetail(article.id)">
                <ul>
                    <li>{{article.title}}<p>{{ article.summary }}</p></li>
                </ul>
            </div>
        </div>

    </div>
</template>
<style scoped>
    .title{
        height: 100vh;
        background-color: rgb(255,255,255,0.5);
        padding-top: 1rem;
        width: 35rem;
        margin: 0 auto;
    }
    h1{
        text-align:center;
    }
    .edit{
        margin-left: 0.5rem;
    }
    .list{
        cursor:pointer;
    }
    ul{
        list-style-type:none;
        padding:0;
    }
    li{
        text-align: center;
        padding:1rem 0;
        color: black;
        font-size: 30px;
    }
    ul p{
        font-size: 20px;
        color: gray;
    }
</style>

<script>


export default {
    data(){
        return{
            articles:[
                {id:1,title:'热点！现在不仅人民币贬值，人民也贬值',summary:'在2024年秋招中,不少学生找不到工作'},
                {id:2,title:'这个世界不是牛马，就是鸡鸭',summary:'草原牛马与城市牛马相见，鸡鸭在微信相见'},
                {id:3,title:'读书是为了什么？',summary:'是为了找到更好的工作，还是说面对选择工作时能有更多种选择'},
                
            ]
        }
    },
    methods:{
        goToDetail(id){
            this.$router.push(`/article/${id}`)
        }
    }
}
</script>