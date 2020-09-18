<template>
<div>
   
    <h3>Tweets</h3>
    <div id=container :class="{tweetStyle:isGrid}" >
    <div  v-for="content in tweets" v-bind:key="content.id">
    <div id="borderStyle">
    <h3>{{ content.content}}</h3>
    <h3>{{ content.name}}</h3>
    <h3>{{ content.date}}</h3>
    </div>
    </div>

    </div>

    
    
    <button @click="isGrid=!isGrid">change view</button>
    

</div>
    
</template>

<script>
export default {
    name:"page-body",
    data: function() {
        return {
            tweets: [{id:1,name:"Joe",content:"With overwhelming pandemic traffic and shutdowns from wildfires, state parks are left with strained resources and tight budgets",date:"01/01/2020"},
            {id:2,name:"John",content:"The current wildfire crisis has been building for decades, and crews are now fighting in unprecedented conditions",date:"02/02/2020"},
            {id:3,name:"Adam",content:"“Leave no trace” is the rallying cry of park rangers everywhere. But at Salt Plains National Wildlife Refuge a more fitting slogan might be “leave big holes”",date:"03/03/2020"},
            {id:4,name:"Annie",content:"Thousands of squirrels are being poached from people’s backyards and funneled into the nation’s largest flying squirrel smuggling enterprise, investigators say",date:"06/04/2020"}],
            isGrid:true
        }
    },
    
}
</script>

<style scoped>
#container {
    text-align: center;
}

.tweetStyle {
    display: grid;
    justify-items: center;
    align-items: center;
    column-gap: 3vw;
    grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
}

#borderStyle{
    border: 1px solid black;
}
</style>