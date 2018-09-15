<template>
    <div id="app">
        <div>{{ title }}</div>
        <div class="uk-flex uk-align-center uk-width-1-3 uk-margin-large">
            <input class="track-input uk-input" placeholder="Введите название трека" v-on:keyup.13="addTrack">
            <button class="uk-button uk-button-secondary" type="button" v-on:click="addTrack"
            >Добавить ещё</button>
        </div>
        <app-list :tracks="tracks"></app-list>
    </div>
</template>

<script>
import List from './List.vue';
export default {
    name: 'app',
    data () {
        return {
            title: 'TODO List',
            tracks: [
                {
                    id: 1,
                    text: 'Nothing Else Matters'
                },
                {
                    id: 2,
                    text: 'Love is blindness'
                },
                {
                    id: 3,
                    text: 'Oh, Children'
                }
            ]
        }
    },
    methods: {
        addTrack() {
            const input = document.querySelector('.track-input');
            const text = input.value;
            const id = this.tracks.length + 1;
            this.tracks.push({id, text});
            input.value = '';
        }
    },
    components: {
       'app-list': List
    },
}
 
</script>

<style lang="scss" scoped>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }

    button {
        white-space: nowrap;
    }

</style>
