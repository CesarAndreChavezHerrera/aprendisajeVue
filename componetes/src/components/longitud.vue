<template>
    <div class="nuevoB">
        <h1>Convetidor de longitud</h1>
        <input type="text" v-model ="entrada_numero" >
        <div >
            <span>De:</span>
        </div>
        <select v-model="fromRate" class= nuevo2>
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
        <select v-model="toRate" class = nuevo3>
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
        <button v-on:click="calcular" class = .p>calcular</button>
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

<style>
.nuevoB {
	background-color: aliceblue;
	background-position: center;
	background-size: cover;
	background-attachment: fixed;
	background-repeat: no-repeat;
}
.nuevo2 {
	width: 50vw;
	margin: auto;
	padding: 15px;
	border-radius: 5px;
	background-color: rgba(0, 238, 255, 0.472);
	color: rgb(0, 0, 0);
}

.nuevo3 {
	width: 50vw;
	margin: auto;
	padding: 15px;
	border-radius: 5px;
	background-color: rgba(0, 255, 157, 0.472);
	color: rgb(0, 0, 0);
}

.p {
  margin-top: 100px;
  margin-bottom: 100px;
  margin-right: 150px;
  margin-left: 80px;
}


</style>