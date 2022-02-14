<template>
    <div class="bodyy">
        <h1>Convetidor de almacenamiento</h1>
      <div class="mainn">  
        <input type="text" v-model ="entrada_numero" >
        <div>
            <span>de:</span>
        </div>
        <select v-model="fromRate">
            <option value="b">byte</option>
            <option value="kb">Kilobyte</option>
            <option value="MB">Megabyte</option>
            <option value="GB">Gigabyte</option>
            <option value="TB">Terabyte</option>
            <option value="PB">Petabyte</option>
            <option value="EB">Exabyte</option>
        </select>
        <br>
        <div>
            <span>Hacia:</span>
        </div>
        <select v-model="toRate">
            <option value="b">byte</option>
            <option value="kb">Kilobyte</option>
            <option value="MB">Megabyte</option>
            <option value="GB">Gigabyte</option>
            <option value="TB">Terabyte</option>
            <option value="PB">Petabyte</option>
            <option value="EB">Exabyte</option>

        </select>
        <br>
        <button v-on:click="calcular">calcular</button>
     </div>
        <h2>Resultado:{{salida}}</h2>
      </div>
</template>

<script>
export default({
    name:"almacenamiento",
    data(){return{
            entrada_numero:"",
            conversiones_gramos:{
                "b":1073741824,
                "kb":1048576,
                "MB":1024,
                "GB":1,
                "TB":0.000977,
                "PB":0.000000954,
                "EB":0.000000000931,
                },    
            salida: "",
            toRate: "b",
            fromRate:"GB"
        }},
    methods:{
            calcular:function(){
                let toRate_ = this.conversiones_gramos[this.toRate]
                let fromRate_ = this.conversiones_gramos[this.fromRate]
                var resultado = ((toRate_/fromRate_))*this.entrada_numero
                this.salida =resultado
            }
        }
})

</script>
<style>
.bodyy {
    background-color: rgb(211, 233, 230);
    background-position: center;
    background-size: cover;
    background-attachment: fixed;
    background-repeat: no-repeat;
}
.mainn {
    width: 50vw;
    margin: auto;
    padding: 30px;
    border-radius: 5px;
    background-color: rgba(0, 17, 255, 0.472);
    color: rgb(0, 0, 0);
}
#Resultado h1 {
    font-size: 40px;
}
</style>
