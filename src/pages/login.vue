<template>
    <q-page class="flex flex-center">
        <div class="row">
            <div class="col">
                <q-input rounded filled v-model="username" label="Name" />
            </div>
            <div class="col">
                 <q-input roundedv-model="password" filled type="password" label="password" hint="Password" />
            </div>
        </div>
        
    </q-page>
</template>

<script>
    export default {
        data(){
            return{
                username:'',
                password:''
            }
        }
    }
</script>

<style scoped>

</style>