<template>
<div class="Body"> 
        <h1>Conversor de masa</h1>
    <div class="Main">
        <div class="form-group">
				<label for="oamount">
					Ingrese su conversión:
				</label>
				<input type="text" v-model="entrada_numero"
					class="form-control searchBox"
					id="oamount" 
                >
			</div>
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
        <button v-on:click="calcular" class="btn btn-calcular">calcular</button>
    </div>
    <div id="Resultado" class="text-center">
        <h2>Resultado:{{salida}}</h2>
        <span class="finalValue"
					style="color:green;">
		</span>
    </div>
</div>
</template>
<script>

export default ({
    name:"Masa",
    data(){
        return{
            entrada_numero:"",
            conversiones_gramos:{ "g":1,"kg":0.001,"onz":0.03528,"lb":0.002205,"T":0.000001102},    
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
<style>
.Body {
	background-color: aliceblue;
	background-position: center;
	background-size: cover;
	background-attachment: fixed;
	background-repeat: no-repeat;
}
.Main {
	width: 50vw;
	margin: auto;
	padding: 30px;
	border-radius: 5px;
	background-color: rgba(255, 0, 0, 0.472);
	color: rgb(0, 0, 0);
}
#Resultado h2 {
	font-size: 45px;
}
</style>