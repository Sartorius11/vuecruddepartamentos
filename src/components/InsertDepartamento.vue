<template>
  <div>
    <h1>Insert Departamentos</h1>
    <h1 style="color:blue">
        Nuevo departamento
    </h1>
    <h1 style="color:red">{{mensaje}}</h1>
    <div style="width:500px; margin:0 auto">
    <form method="post" v-on:submit.prevent="insertarDepartamento()">
        <label>Numero: </label>
        <input type="number" class="form-control"
        v-model="departamento.numero"><br/>

        <label>Nombre: </label>
        <input type="text" class="form-control"
        v-model="departamento.nombre"><br/>

        <label>Localidad</label>
        <input type="text" class="form-control"
        v-model="departamento.localidad"><br/>

        <button class="btn btn-info">Create</button>

    </form>
    </div>
    </div>
</template>

<script>
import ServicesDepartamentos from './../services/ServicesDepartamentos';
 const service = new ServicesDepartamentos();

export default {
    name:"InsertDepartamentos",
    methods:{
        insertarDepartamento(){
            service.insertarDepartamento(this.departamento).then(result=>{
                console.log(result)
                this.mensaje="Insertado, OK!";
                //te devuelve a la ruta
                this.$router.push("/");
            });
        }
    }
    
    
    ,data(){
        return{
            mensaje:"",
            departamento:{
                numero:0,
                nombre:"",
                localidad:""
            }
        }
    }

}
</script>

