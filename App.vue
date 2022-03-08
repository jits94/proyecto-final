<template>
  <navegacion></navegacion>
</template>

<script>
  import {createAppContainer,createStackNavigator} from "vue-native-router";

  import InicioScreen from "./screens/Inicio.vue";
  import ContabilidadScreen from "./screens/Contabilidad.vue";
  import HistorialingresosScreen from "./screens/Historial-Ingresos.vue";
  import HistorialegresosScreen from "./screens/Historial-egresos.vue";
  
  const StackNavigator = createStackNavigator(
    {
      Inicio: InicioScreen,
      Contabilidad: ContabilidadScreen,
      ingresos:HistorialingresosScreen,
      egresos:HistorialegresosScreen,
    },
    {
      initialRouteName: 'Inicio'
    }
  );
  const Navegacion = createAppContainer(StackNavigator);
  
  export default {
    components: { Navegacion }
  
  }
</script>