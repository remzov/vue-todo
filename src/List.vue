<template>
    <div>
     <ul class="uk-list">
        <li v-for="track in tracks" v-bind:key="track.id">
        {{ track.text }}
        </li> 
    </ul> 
    </div>
</template>

<script>
export default {
    props: ['tracks']
}

</script>

<style>
</style>