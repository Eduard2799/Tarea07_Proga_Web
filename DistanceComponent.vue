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
                <option value=0>Metros</option>
                <option value=1>Kilómetros</option>
                <option value=2>Millas</option>
                <option value=3>Yardas</option>
                <option value=4>Pies</option>
                <option value=5>Pulgadas</option>
            </select>
            <div id="emailHelp" class="form-text">Seleccione la unidad inicial.</div>
            <label for="exampleInputEmail1" class="form-label">Unidad final</label>
            <select class="form-select bg-success" v-model="fin" v-on:change="convertir()">
                <option value=0>Metros</option>
                <option value=1>Kilómetros</option>
                <option value=2>Millas</option>
                <option value=3>Yardas</option>
                <option value=4>Pies</option>
                <option value=5>Pulgadas</option>
            </select>
            <div id="emailHelp" class="form-text">Seleccione la unidad final.</div>
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
                            this.result = this.value / 1000;
                        }else if(this.inicio == 0 && this.fin == 2){
                            this.result = this.value / 1609;
                        }else if(this.inicio == 0 && this.fin == 3){
                            this.result = this.value * 1,094;
                        }else if(this.inicio == 0 && this.fin == 4){
                            this.result = this.value * 3,281;
                        }else if(this.inicio == 0 && this.fin == 5){
                            this.result = this.value * 39,37;
                        }
                    }else if (this.inicio == 1){
                        if(this.inicio == 1 && this.fin == 0){
                            this.result = this.value * 1000;                         
                        }else if(this.inicio == 1 && this.fin == 2){
                            this.result = this.value / 1,609;
                        }else if(this.inicio == 1 && this.fin == 3){
                            this.result = this.value * 1094;
                        }else if(this.inicio == 1 && this.fin == 4){
                            this.result = this.value * 3281;
                        }else if(this.inicio == 1 && this.fin == 5){
                            this.result = this.value * 39370;
                        }
                    }else if(this.inicio == 2){

                        if(this.inicio == 2 && this.fin == 0){
                            this.result = this.value * 1609;                         
                        }else if(this.inicio == 2 && this.fin == 1){
                            this.result = this.value * 1,609;
                        }else if(this.inicio == 2 && this.fin == 3){
                            this.result = this.value * 1760;
                        }else if(this.inicio == 2 && this.fin == 4){
                            this.result = this.value * 5280;
                        }else if(this.inicio == 2 && this.fin == 5){
                            this.result = this.value * 63360;
                        }
                    }else if(this.inicio == 3){
                        if(this.inicio == 3 && this.fin == 0){
                            this.result = this.value / 1,094;                         
                        }else if(this.inicio == 3 && this.fin == 1){
                            this.result = this.value / 1094;
                        }else if(this.inicio == 3 && this.fin == 2){
                            this.result = this.value / 1760;
                        }else if(this.inicio == 3 && this.fin == 4){
                            this.result = this.value * 3;
                        }else if(this.inicio == 3 && this.fin == 5){
                            this.result = this.value * 36;
                        }
                    }else if(this.inicio == 4){
                        if(this.inicio == 4 && this.fin == 0){
                            this.result = this.value / 3,281;                         
                        }else if(this.inicio == 4 && this.fin == 1){
                            this.result = this.value / 3281;
                        }else if(this.inicio == 4 && this.fin == 2){
                            this.result = this.value / 5280;
                        }else if(this.inicio == 4 && this.fin == 3){
                            this.result = this.value / 3;
                        }else if(this.inicio == 4 && this.fin == 5){
                            this.result = this.value * 12;
                        }
                    }else if(this.inicio == 5){
                        if(this.inicio == 5 && this.fin == 0){
                            this.result = this.value / 39,37;                         
                        }else if(this.inicio == 5 && this.fin == 1){
                            this.result = this.value / 39370;
                        }else if(this.inicio == 5 && this.fin == 2){
                            this.result = this.value / 63360;
                        }else if(this.inicio == 5 && this.fin == 3){
                            this.result = this.value * 36;
                        }else if(this.inicio == 5 && this.fin == 4){
                            this.result = this.value * 12;
                        }
                    }
                }
            } 
        } 
    
    }
</script>