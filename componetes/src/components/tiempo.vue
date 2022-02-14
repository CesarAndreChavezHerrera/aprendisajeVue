<template>
    <div class="Body" style="background:#DADF27">
        <br>
        <h1>Convertidor de unidades de tiempo</h1>


        <div class="Main">
            <input type="text" v-model ="entrada_numero" >
        <div>
            <span>DE:</span>
        </div>
        <select v-model="fromRate">
            <option value="años">años</option>
            <option value="meses">meses</option>
            <option value="semanas">semanas</option>
            <option value="dias">dias</option>
            <option value="horas">horas</option>
            <option value="minuto">minuto</option>
            <option value="segundos">segundos</option>
            <option value="milisegundos">milisegundos</option>
            <option value="microsegundos">microsegundos</option>
            <option value="nanosegundos">nanosegundos</option>
        </select>
        <br>
        <div>
            <span>HACIA:</span>
        </div>
        <select v-model="toRate">
            <option value="años">años</option>
            <option value="meses">meses</option>
            <option value="semanas">semanas</option>
            <option value="dias">dias</option>
            <option value="horas">horas</option>
            <option value="minuto">minuto</option>
            <option value="segundos">segundos</option>
            <option value="milisegundos">milisegundos</option>
            <option value="microsegundos">microsegundos</option>
            <option value="nanosegundos">nanosegundos</option>
        </select>
        <br>
        <button v-on:click="calcular">calcular</button>
        <h2>{{entrada_numero}} {{fromRate}} equivalen a {{salida}} {{toRate}}</h2>
      

        </div>
    </div>
</template>

<script>
export default({
    name:"tiempo",
    data(){return{
            entrada_numero:"",
            conversiones_gramos:{   "años":0.0000000317,"meses":0.00000038,"semanas":0.00000165,"dias":0.0000116,"horas":0.00027799999999999998,"minuto":0.016666666666667,"segundos":1, "milisegundos":1000,"microsegundos":1000000,"nanosegundos":1000000000},    
            salida: "",
            toRate: "",
            fromRate:""
        }},
    methods:{
            calcular:function(){
                let toRate_ = this.conversiones_gramos[this.toRate]
                let fromRate_ = this.conversiones_gramos[this.fromRate]
                var resultado = (((toRate_/fromRate_))*this.entrada_numero).toFixed(3)
                this.salida =resultado
            }
        }
})

</script>
