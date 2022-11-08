<template>
    <div>
        <h1>DELETE</h1>

    </div>
</template>
<script>
import ServiceDepartamentos from './../services/ServicesDepartamentos';
const service = new ServiceDepartamentos();
export default {
    
    name:"DeleteDepartamentos",
    mounted(){
        var id= this.$route.params.id;
        service.deleteDepartamento(id).then(result=>{
            console.log(result);
            this.$router.push("/");
        })
    }
}
</script>
<style>
    
</style>