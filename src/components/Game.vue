<template>
    <div>
        <GameGrid :name="name"/>
    </div>
</template>

<script>
import GameGrid from './GameGrid'

export default {
    name: 'Game',
    props: ['name'],
    data() {
        return {
            online_users: []
        }
    },
    methods: {
        exit(){
        
        }
    },
    created() {
        window.addEventListener('beforeunload', this.exit);
        window.addEventListener('popstate', this.exit);
    },
    beforeDestroy() {
        window.removeEventListener('beforeunload', this.exit)
        window.removeEventListener('popstate', this.exit)
    },
    components: {
        GameGrid
    }
}
</script>

<style>
   
   .online_users p{
       margin: 0;
}
</style>