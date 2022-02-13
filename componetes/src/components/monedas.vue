<template>
	
    
	<div class="body">
		<h1 class="heading text-center display-2">Conversor de Monedas</h1>

	<div class="container">

		<div class="main">

			<div class="form-group">
				<label for="oamount">
					Cantidad a Convertir:
				</label>
				<input type="text"
					class="form-control searchBox"
					placeholder="0.00"
					id="oamount"
                    v-model="texto_entrada"
                    >
			</div>

			<div class="row">
				<div class="col-sm-6">
					<div class="input-group mb-3">
						<div class="input-group-prepend">
							<span class="input-group-text">DE:</span>
						</div>
						<select class="form-control from" id="sel1" v-model="fromRate">
							<option value="">Selecciona una …</option>
							<option value="USD">USD</option>
							<option value="AED">AED</option>
							<option value="ARS">ARS</option>
							<option value="AUD">AUD</option>
							<option value="BGN">BGN</option>
							<option value="BRL">BRL</option>
							<option value="BSD">BSD</option>
							<option value="CAD">CAD</option>
							<option value="CHF">CHF</option>
							<option value="CLP">CLP</option>
							<option value="CNY">CNY</option>
							<option value="COP">COP</option>
							<option value="CZK">CZK</option>
							<option value="DKK">DKK</option>
							<option value="DOP">DOP</option>
							<option value="EGP">EGP</option>
							<option value="EUR">EUR</option>
							<option value="FJD">FJD</option>
							<option value="GBP">GBP</option>
							<option value="GTQ">GTQ</option>
							<option value="HKD">HKD</option>
							<option value="HRK">HRK</option>
							<option value="HUF">HUF</option>
							<option value="IDR">IDR</option>
							<option value="ILS">ILS</option>
							<option value="INR">INR</option>
							<option value="ISK">ISK</option>
							<option value="JPY">JPY</option>
							<option value="KRW">KRW</option>
							<option value="KZT">KZT</option>
							<option value="MVR">MVR</option>
							<option value="MXN">MXN</option>
							<option value="MYR">MYR</option>
							<option value="NOK">NOK</option>
							<option value="NZD">NZD</option>
							<option value="PAB">PAB</option>
							<option value="PEN">PEN</option>
							<option value="PHP">PHP</option>
							<option value="PKR">PKR</option>
							<option value="PLN">PLN</option>
							<option value="PYG">PYG</option>
							<option value="RON">RON</option>
							<option value="RUB">RUB</option>
							<option value="SAR">SAR</option>
							<option value="SEK">SEK</option>
							<option value="SGD">SGD</option>
							<option value="THB">THB</option>
							<option value="TRY">TRY</option>
							<option value="TWD">TWD</option>
							<option value="UAH">UAH</option>
							<option value="UYU">UYU</option>
							<option value="ZAR">ZAR</option>
						</select>
					</div>
				</div>

				<div class="col-sm-6">
					<div class="input-group mb-3">
						<div class="input-group-prepend">
							<span class="input-group-text">Hacia:</span>
						</div>
						<select class="form-control to" id="sel2" v-model="toRate">
							<option value="">Selecciona una …</option>
							<option value="USD">USD</option>
							<option value="AED">AED</option>
							<option value="ARS">ARS</option>
							<option value="AUD">AUD</option>
							<option value="BGN">BGN</option>
							<option value="BRL">BRL</option>
							<option value="BSD">BSD</option>
							<option value="CAD">CAD</option>
							<option value="CHF">CHF</option>
							<option value="CLP">CLP</option>
							<option value="CNY">CNY</option>
							<option value="COP">COP</option>
							<option value="CZK">CZK</option>
							<option value="DKK">DKK</option>
							<option value="DOP">DOP</option>
							<option value="EGP">EGP</option>
							<option value="EUR">EUR</option>
							<option value="FJD">FJD</option>
							<option value="GBP">GBP</option>
							<option value="GTQ">GTQ</option>
							<option value="HKD">HKD</option>
							<option value="HRK">HRK</option>
							<option value="HUF">HUF</option>
							<option value="IDR">IDR</option>
							<option value="ILS">ILS</option>
							<option value="INR">INR</option>
							<option value="ISK">ISK</option>
							<option value="JPY">JPY</option>
							<option value="KRW">KRW</option>
							<option value="KZT">KZT</option>
							<option value="MVR">MVR</option>
							<option value="MXN">MXN</option>
							<option value="MYR">MYR</option>
							<option value="NOK">NOK</option>
							<option value="NZD">NZD</option>
							<option value="PAB">PAB</option>
							<option value="PEN">PEN</option>
							<option value="PHP">PHP</option>
							<option value="PKR">PKR</option>
							<option value="PLN">PLN</option>
							<option value="PYG">PYG</option>
							<option value="RON">RON</option>
							<option value="RUB">RUB</option>
							<option value="SAR">SAR</option>
							<option value="SEK">SEK</option>
							<option value="SGD">SGD</option>
							<option value="THB">THB</option>
							<option value="TRY">TRY</option>
							<option value="TWD">TWD</option>
							<option value="UAH">UAH</option>
							<option value="UYU">UYU</option>
							<option value="ZAR">ZAR</option>
						</select>
					</div>
				</div>
			</div>

			<div class="text-center">

				
				<button class="btn btn-primary convert m-2"
						
                        v-on:click="calcular"
                        >
					Convertir
                    </button>

				
				<button class="btn btn-primary m-2"
						v-on:click = "resetear">
				Resetear
			</button>
			</div>

		</div>

		<div id="finalAmount" class="text-center">

			
			<h2>Cantidad convertida :{{texto_salida}}
				<span class="finalValue"
					style="color:green;">
		</span>
			</h2>
		</div>
	</div>

	</div>
    
</template>

<script>
const api = "https://api.exchangerate-api.com/v4/latest/USD";
    
export default {
    name:"monedas",
    data(){
            return{
            texto_salida:"",
            texto_entrada:"",
            toRate :"EUR",
            fromRate:"USD"
            }
        },
        methods:{
            calcular:function(){
                
                fetch(`${api}`).then(dato =>{
                    return dato.json();
                }).then(dato=>{
                    let rate_from = dato.rates[this.fromRate]
                    let rate_to = dato.rates[this.toRate]
                    this.texto_salida = ((rate_to/rate_from)*this.texto_entrada).toFixed(2)
                    
                })
            

            },
            test_:function(){
                alert("test")
            }  ,
			resetear:function(){
				this.texto_entrada = ""



			}         
        }

}
</script>
<style>
.body {
	background-color: aliceblue;
	background-position: center;
	background-size: cover;
	background-attachment: fixed;
	background-repeat: no-repeat;
}
    .heading {
	font-family: 'Pacifico', cursive;
	margin: 35px auto 20px;
}

hr {
	border-top: 2px solid black;
	width: 40%;
	margin-bottom: 55px;
}

.main {
	width: 50vw;
	margin: auto;
	padding: 30px;
	border-radius: 5px;
	background-color: rgba(0, 0, 0, 0.5);
	color: white;
}

label {
	font-size: 20px;
}

.btn {
	width: 200px;
}

#finalAmount {
	font-family: 'Lobster', cursive;
	/*display: none;*/
	margin: 50px auto;
}

#finalAmount h2 {
	font-size: 50px;
}

.finalValue {
	font-family: 'Amiri', serif;
}

@media (max-width: 768px) {
	hr {
		width: 60%;
	}
	.main {
		width: 100%;
	}
}

@media (max-width: 400px) {
	.heading {
		font-size: 60px;
	}
	hr {
		width: 75%;
	}
	#finalAmount h2, .finalValue {
		font-size: 40px;
	}
}

</style>