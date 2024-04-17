<script>
import AppSelect from './AppSelect.vue'
export default {
    name : 'AppHeader',
    components : {
        AppSelect
    }
}
</script>
<template>
    <div class="d-flex justify-content-between p-2">
        <div>
            <h1>Boolfix</h1>
        </div>
        <AppSelect></AppSelect>

        
    </div>

</template>

<style scoped lang="scss">
h1{
    color : red
}
</style>