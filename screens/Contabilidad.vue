<template>
   <view class="container">
     <text class="titulo">  <image
          :style="{width: 50, height: 40}"
          :source="{uri: 'https://www.garridofreshmentoring.com/wp-content/uploads/2016/01/dreamstime_m_53432685-min-300x300.jpg'}"
        /> Registrar Datos</text>
    <text class="etiqueta">Detalle</text>
    <text-input
          class="estilox"
          v-model="text1"
          placeholder="Ingresar detalle del registro"
    />

    <text class="etiqueta">Costo</text>
    <text-input
          class="estilox"
          v-model="text2"
          placeholder="Ingresar costo total"
    />
    <text class="etiqueta">Tipo: - Egreso y + Ingreso</text>
    <text-input
          class="estilox"
          v-model="text3"
          placeholder="Ingresar + para ingreso o - para egreso"
    />
    <view class="boton">
      <button title="Guardar" @press="guardar"></button>
    </view>
  </view> 
</template>




<script>
//import { NativeBaseProvider,Button, Box,Container, Text,Heading,Select, Stack, HStack, Center, Input, ScrollView, VStack} from "./../native-base";
import axios from "axios";

    export default {        
        data: function() {
            return {
              datos:null,
              text1:null,
              text2:null,
              text3:null,
           
            };
        },   
        //components:{NativeBaseProvider,Button, Box, Container, Text, Heading,Select, Stack, HStack, Center,Input,ScrollView, VStack},     
        methods:{
          guardar(){

            if(this.text1 == null || this.text2 == null || this.text3==null){
              alert("Debe rellenar todos los campos");
            }
            else{
              axios.post('http://tecnoprofe.com/api/contabilidad',
              {
                "id":10,
                "detalle":this.text1,
                "precio":this.text2,
                "tipo":this.text3            
              })
              .then((response)=>{
                alert("Registro Satisfactorio");
                this.text1 = "";
                this.text2 = "";
                this.text3="";
              });
                
            }
          },
          ingresar(){
            alert(this.categoria)
          },
        },
        mounted () {
          axios.get('http://tecnoprofe.com/api/contabilidad')
          .then(response => (this.datos = response.data))
        }
    }

</script>




<style>
.container {
  flex: 1;
  font-size:80px;
  text-align:right;
  color:black;
  display:flex;
}
.text-color-primary {
  color: blue;
}
.estilox {
  color:black;
  width:320px;  
  height:40px;
  font-size:15px;
  display:flex;
  margin-left: 20px;
  background-color: #ffffff;
  margin-bottom: 20px;
  border-width: 1px;
  border-color:cornflowerblue;
  border-radius: 7px;
  padding-left: 10px;
}
.etiqueta{
  margin-left: 20px;
 font-size:17px;
}
.titulo{
  margin-left: 12%;
 font-size:30px;
margin-top:20px;
margin-bottom:20px;
}
.boton{
  margin-top: 20px;
  width: 320px;
  margin-left: 20px;
}
</style>