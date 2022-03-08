<template>
 <scroll-view :content-container-style="{contentContainer: { paddingVertical: 20}}">
  <view>
      <text class="titulo"> <image
          :style="{width: 70, height: 40}"
          :source="{uri: 'https://www.iebschool.com/blog/wp-content/uploads/2014/05/FINANZAS-2-768x469.jpg'}"
        /> Historial de Ingresos</text>
      <text class="tituloTabla"> DETALLE COSTO TIPO</text>
      <text v-for="dato in datos">
        <text class="tituloTabla" v-if="dato.tipo == '+'"> 
        {{dato.detalle}}      {{dato.precio}}     {{dato.tipo}}</text>
      </text>
    </view>
  </scroll-view>
</template>

<script>
//import { NativeBaseProvider,Button, Box,Container, Text,Heading,Select, Stack, HStack, Center, Input, ScrollView, VStack} from "native-base";
import axios from "axios";

    export default {        
        data: function() {
            return {
              datos:null,
            };
        },   
       // components:{NativeBaseProvider,Button, Box, Container, Text, Heading,Select, Stack, HStack, Center,Input,ScrollView, VStack},     
        methods:{

        },
        mounted () {
          axios.get('http://tecnoprofe.com/api/contabilidad')
          .then(response => (this.datos = response.data))
        }
    }

</script>

<style>
.titulo{
  margin-left: 5%;
 font-size:25px;
margin-top:20px;
margin-bottom:20px;
}
.tituloTabla{
  flex-direction: row;
  margin-left:20px;
}
.datosTabla{
  
  flex-direction: row;
}
</style>