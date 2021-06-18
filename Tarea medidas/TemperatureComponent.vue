<template id="conversor-tmpl">

    <div class="container mt-5 bg-info">

        <center>
            <div class="mb-3 col-5">
                <label for="exampleInputEmail1" class="form-label">Cantidad</label>
                <input type="email"  v-model="value" class="form-control bg-success" v-on:keyup="convertir()" id="exampleInputEmail1" aria-describedby="emailHelp">
                <div id="emailHelp" class="form-text">Recuerde que solo puede ingresar numeros.</div>
            </div>

            <div class="col-5">
                <label for="exampleInputEmail1" class="form-label">Unidad inicial</label>
                    <select class="form-select bg-success" v-model="inicio" v-on:change="convertir()">
                    <option value=0>Celcius</option>
                    <option value=1>Fahrenheit</option>
                    <option value=2>Rankine</option>
                    <option value=3>Kelvin</option>
                </select>
                <div id="emailHelp" class="form-text">Seleccione la unidad inicial.</div>
                <label for="exampleInputEmail1" class="form-label">Unidad final</label>
                <select class="form-select bg-success" v-model="fin" v-on:change="convertir()">
                    <option value=0>Celcius</option>
                    <option value=1>Fahrenheit</option>
                    <option value=2>Rankine</option>
                    <option value=3>Kelvin</option>
                </select>

                <br>
                <div class="alert alert-success" role="alert">
                    Resultado: {{result}}
                </div>
                <br>
            </div>
            
        </center>

    </div>

</template>

<script>
    module.exports = {
        data: function () {
            return {
                inicio: 0,
                fin: 0,
                value: 0,
                result: ''
            }
        },
        methods: {   
            convertir: function(){
                this.value = parseInt(this.value);

                if(this.inicio == this.fin){
                    this.result = this.value;
                }else{
                    
                    if (this.inicio == 0) {
                        if(this.inicio == 0 && this.fin == 1){
                            this.result = (this.value * 9/5) + 32;
                        }else if(this.inicio == 0 && this.fin == 2){
                            this.result = this.value + 9/5 + 491.67;
                        }else if(this.inicio == 0 && this.fin == 3){
                            this.result = this.value + 273.15;
                        }
                    }else if (this.inicio == 1){
                        if(this.inicio == 1 && this.fin == 0){
                            this.result = (this.value - 32) * 5/9;                         
                        }else if(this.inicio == 1 && this.fin == 2){
                            this.result = this.value + 459.67;
                        }else if(this.inicio == 1 && this.fin == 3){
                            this.result = (this.value - 32) * 5/9 + 273.15;
                        }
                    }else if(this.inicio == 2){
                        if(this.inicio == 2 && this.fin == 0){
                            this.result = (this.value - 491.67) * 5/9;                         
                        }else if(this.inicio == 2 && this.fin == 1){
                            this.result = this.value - 459.67;
                        }else if(this.inicio == 2 && this.fin == 3){
                            this.result = this.value * 5/9;
                        }
                    }else if(this.inicio == 3){
                        if(this.inicio == 3 && this.fin == 0){
                            this.result = this.value - 273.15;                         
                        }else if(this.inicio == 3 && this.fin == 1){
                            this.result = (this.value - 273.15) * 9/5 + 32;
                        }else if(this.inicio == 3 && this.fin == 2){
                            this.result = (this.value - 273.15) * 1.8;
                        }
                    }

                }
            } 
        } 
    
    }
</script>