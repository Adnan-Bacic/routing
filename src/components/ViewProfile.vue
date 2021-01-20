<template>
    <div class="view-profile">
        <h1>Profile for {{ userID }}</h1>
    </div>
</template>

<script>
export default {
    name: 'ViewProfile',

    data(){
        return{
            userID: this.$route.params.user_id
        }
    },
    methods:{
        updateID(){
            this.userID = this.$route.params.user_id
            //alert('test')
        }
    },
    watch:{
        $route: 'updateID'
    }
}
</script>

<style scoped>

</style>