
<template>
    <ul>
        <li v-for="ninja in ninjas" :key="ninja">{{ ninja }}</li>
    </ul>
</template>

<script>
export default {
    data () {
        return {
          ninjas: ['Yoshi', 'Mario', 'Ryu' ,'something']
        }
    }
}
</script>

<style>
</style>