<template>
    <div>
        <h1>Conversor de masa</h1>
        <input type="text" v-model ="entrada_numero" >
        <div>
            <span>De:</span>
        </div>
        <select v-model="fromRate">
            <option value="g">Gramos</option>
            <option value="kg">Kilogramo</option>
            <option value="onz">Onzas</option>
            <option value="lb">libras</option>
            <option value="T">Tonelada</option>
        </select>
        <div>
            <span>Hacia:</span>
        </div>
        <select v-model="toRate">
            <option value="g">Gramos</option>
            <option value="kg">Kilogramo</option>
            <option value="onz">Onzas</option>
            <option value="lb">libras</option>
            <option value="T">Tonelada</option>
        </select>
        <br>
        <button v-on:click="calcular">calcular</button>
        <h2>resultado:{{salida}}</h2>
    </div>
</template>
<script>

export default ({
    name:"Masa",
    data(){
        return{
            entrada_numero:"",
            conversiones_gramos:{ "g":1,"kg":0.001,"onz":0.0237,"lb":0.002205,"T":0.000001102},    
            salida: "",
            toRate: "g",
            fromRate:"kg"
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
