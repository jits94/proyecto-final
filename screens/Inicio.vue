<template>
  <view class="container">
    <text class="titulo">REGISTRO DE INGRESO Y EGRESOS</text>
    
    <view class="image">
       <image
          :style="{width: 300, height: 330}"
          :source="{uri: 'https://revista.condusef.gob.mx/wp-content/uploads/2016/12/images_psd_202_basicos.jpg'}"
        />
    </view>
    <image
        :source="{uri: 'https://e7.pngegg.com/pngimages/634/484/png-clipart-money-finance-icon-free-to-pull-the-dollar-sign-creative-3d-computer-graphics-free-logo-design-template.png'}"
        class="imagestyle"
      />
    <button title="Nuevo Registro" @press="rutacontabilidad" ></button>
    <view class="botones">
       <view class="boton">
          
        <button title="Historial Egresos" @press="rutaHistorialEgresos"></button>
       </view>
      <button title="Historial Ingresos" @press="rutaHistorialIngresos"></button>
    </view>
  </view>
</template>

<script>
import { Ionicons } from "@expo/vector-icons";
import Vue from "vue-native-core";
Vue.component("ionicons", Ionicons);


export default {
  
  props: {
    navigation: { type: Object }
  },
  methods: {
    rutacontabilidad() {
      this.navigation.navigate('Contabilidad');
    },
    rutaHistorialIngresos() {
      this.navigation.navigate('ingresos');
    },
    rutaHistorialEgresos() {
      this.navigation.navigate('egresos');
    }
  },
  components: {Ionicons},
  
}
</script>

<style>
.container {
  align-items: center;
  justify-content: center;
  flex: 1;  
}
.titulo{
  flex:1;
  font-size: 30px;
  margin: 3%;
  text-align: center;
}
.botones{
  margin-bottom: 20px;  
  flex-direction: row;
  margin-top: 10px;
}
.boton{
  margin-right: 5px;
}
.image{
  flex:1;
  margin-bottom: 290px;
  margin-right: 90px;
}
</style>