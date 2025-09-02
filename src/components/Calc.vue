<script>
export default{
    data(){
        return{
            seven: 7,
            UserInput: "",
            Res:"",
            Errors: ""
        }
    },
    methods:{
        UserValue(val){
            this.UserInput = val
        },
        GetResult(val){
            if(this.UserInput == ""){
                this.Errors = "Ошибка! Введите выражение"
                return false
            }
            else if(this.UserInput.startsWith('abs')){
                
                let numToEvaluate = this.UserInput.slice(3);
                try{
                    this.Res = Math.abs(eval(numToEvaluate));
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                } 
            }
            else if(this.UserInput.startsWith('sin')){
                let numToEvaluate = this.UserInput.slice(3)
                try{
                    this.Res = Math.sin(eval(numToEvaluate))
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else if(this.UserInput.startsWith("cos")){
                let numToEvaluate = this.UserInput.slice(3)
                try{
                    this.Res = Math.cos(eval(numToEvaluate))
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else if(this.UserInput.startsWith("tan")){
                let numToEvaluate = this.UserInput.slice(3)
                try{
                    this.Res = Math.tan(eval(numToEvaluate))
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else if(this.UserInput.startsWith("floor")){
                let numToEvaluate = this.UserInput.slice(5)
                try{
                    this.Res = Math.floor(eval(numToEvaluate))
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else if(this.UserInput.startsWith("ceil")){
                let numToEvaluate = this.UserInput.slice(4)
                try{
                    this.Res = Math.ceil(eval(numToEvaluate))
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else if(this.UserInput.startsWith("sqrt")){
                let numToEvaluate = this.UserInput.slice(4)
                try{
                    this.Res = Math.sqrt(eval(numToEvaluate))
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else if(this.UserInput.startsWith("log")){
                let numToEvaluate = this.UserInput.slice(3)
                try{
                    this.Res = Math.log(eval(numToEvaluate))
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else if(this.UserInput.startsWith("PI")){
                let numToEvaluate = this.UserInput.slice(2)
                try{
                    this.Res = 3.14
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else if(this.UserInput.startsWith("e")){
                let numToEvaluate = this.UserInput.slice(2)
                try{
                    this.Res = 2.72
                    this.Errors = ""
                } catch(e){
                    this.Errors = e.message
                }
            }
            else{
                this.Errors = ""
                this.Res = eval(val)
            }     
        }
    }
}
</script>
<template>
  <div class="Calculate">
    <label className="text-primary fs-1 fw-bolder">Введите выражение:</label>
    <input v-model="UserInput" type="text" className="form-control mt-5">
    <button class="btn btn-primary btn-lg mt-5" v-on:click="GetResult(UserInput)">Рассчитать выражение</button>
    <p v-show="UserInput == ''" className="fs-1 fw-bolder text-danger">{{ Errors }}</p>
    <p v-show="UserInput != ''" className="text-primary fs-1">Результат: {{ Res }}</p>
  </div>
</template>

<style scoped>
.Calculate{
    width: 750px;
    height: 500px;
    background-color: #261e1d;
    margin-left: 30%;
    margin-top: 5%;
}
.d-flex{
    gap:10px;
}
</style>