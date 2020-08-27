<template>
    <div id="grid-images">
        <div class="ui card my-ig-card" v-for="(username, i) in usernames" :key="i">
            <div class="content">
                <div class="right floated meta">14h</div>
                <img class="ui avatar image" :src="apis.data.message[i]">
                <b>{{ username }}</b> 
            </div>
            <div class="image">
                <img :src="apis.data.message[i]">
            </div>
            <div class="content">
                <span class="right floated">
                <i class="heart outline like icon"></i>
                17 likes
                </span>
                <i class="comment icon"></i>
                3 comments
            </div>
            <div class="extra content">
                <div class="ui large transparent left icon input">
                <i class="heart outline icon"></i>
                <input type="text" placeholder="Add Comment...">
                </div>
            </div>
        </div>

      
    </div>
    
</template>

<script>
import axios from 'axios';
export default {
    name: 'GridImages',
    data: function() {
        return {
            avatarImg: 'https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4',
            usernames: ['Kea','Aung', 'Praw', 'Whan', 'Film'],
            apis: null,
            fakeApi: null

        }
    },
    mounted: function() {
        axios
        .get('https://dog.ceo/api/breed/pomeranian/images/random/10')
        .then(response => this.apis = response)

        
    }
}
</script>

<style>
    #grid-images {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
    }
</style>