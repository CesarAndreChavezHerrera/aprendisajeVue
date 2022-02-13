<template>
    <div>
        <h1>Convetidor de logitud</h1>
        <input type="text" v-model ="entrada_numero" >
        <div>
            <span>Hacia:</span>
        </div>
        <select v-model="fromRate">
            <option value="mm">mm</option>
            <option value="cm">cm</option>
            <option value="dm">dm</option>
            <option value="m">m</option>
            <option value="dam">dam</option>
            <option value="hm">hm</option>
            <option value="km">km</option>
            <option value="ft">ft</option>
            <option value="in">in</option>
            <option value="yd">in</option>
            <option value="nmi">nmi</option>
        </select>
        <br>
        <div>
            <span>Hacia:</span>
        </div>
        <select v-model="toRate">
            <option value="mm">mm</option>
            <option value="cm">cm</option>
            <option value="dm">dm</option>
            <option value="m">m</option>
            <option value="dam">dam</option>
            <option value="hm">hm</option>
            <option value="km">km</option>
            <option value="ft">ft</option>
            <option value="in">in</option>
            <option value="yd">in</option>
            <option value="nmi">nmi</option>
        </select>
        <br>
        <button v-on:click="calcular">calcular</button>
        <h2>resultado:{{salida}}</h2>
    </div>
</template>
<script>

export default({
    name:"longitud",
     data(){return{
            entrada_numero:"",
            conversiones_gramos:{   "mm":1000,"cm":100,"dm":10,"m":1,"dam":0.1,"hm":0.01,"km":0.001, "ft":3.2808,"in":39.3701,"yd":1.0936,"nmi":0.00053996},    
            salida: "",
            toRate: "km",
            fromRate:"m"
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
