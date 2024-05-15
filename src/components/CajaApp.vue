<template>
    <!--Título-->
    <div class="row d-flex justify-content-center mt-3">
        <div class="col-sm-4 d-flex justify-content-center">
            <h1 class="text-primary">{{ nombreCliente }}</h1>
        </div>
    </div>
    <!--Contenido-->
    <div class="row">
        <!--Formulario-->
        <div class="col-sm-6 p-5">
            <div>
                <div class="mb-3">
                    <label class="form-label">Nombre</label>
                    <input v-model="nombreCliente" type="text" class="form-control">
                </div>
                <div class="mb-3">
                    <label class="form-label">Producto</label>
                    <select v-model="idSeleccionar" @change="comprobar" type="text" class="form-control">
                        <option value="0">-- seleccione --</option>
                        <option v-for="producto in productos" :value="producto.id">{{ producto.nombre }}</option>
                    </select>
                </div>
                <div class="mb-3">
                    <label class="form-label">Cantidad</label>
                    <input v-model="cantidad" type="number" class="form-control">
                </div>
                <div class="mb-3">
                    <button class="btn btn-primary">
                        Agregar
                    </button>
                </div>
            </div>
        </div>
        <!--Resultado-->
        <div class="col-sm-6 mt-5 p-5">
            <table class="table table-bordered">
                <thead>
                    <tr>
                        <td>Producto</td>
                        <td>Cantidad</td>
                        <td>Valor</td>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Harina</td>
                        <td align="right">1</td>
                        <td align="right">$ 4000</td>
                    </tr>
                    <tr>
                        <td>Subtotal</td>
                        <td colspan="2"></td>
                    </tr>
                    <tr>
                        <td>IVA</td>
                        <td colspan="2"></td>
                    </tr>
                    <tr>
                        <td>TOTAL</td>
                        <td colspan="2"></td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script lang="ts">

 export default{
    name :'CajaApp',
    data(){
        return{
            productos: [
            {
                id:1,
                nombre: 'Aceite',
                valor: '1000'
            },
            {
                id:2,
                nombre: 'Harina',
                valor: '4000'
            },
            {
                id:3,
                nombre: 'Frijol',
                valor: '3000'
            },
            {
                id:4,
                nombre: 'Gelatina',
                valor: '2000'
            },
            ],
            nombreCliente:'',
            cantidad:1,
            idSeleccionar:0
        }
    },
    computed:{
        seleccionar(){
            return this.productos.find((element) => element.id == this.idSeleccionar)
        }
    },
    methods:{
        comprobar(){
            console.log('Seleccionado', this.seleccionar)
        }
    }
}

</script>
<style lang="scss">

</style>