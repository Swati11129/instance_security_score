<template>
  <v-app>
    
       <InstanceSecurityScore />
      <!-- <router-view/> -->
    
  </v-app>
</template>

<script>
import InstanceSecurityScore from './components/InstanceSecurityScore.vue'
export default {
  name: 'App',
  
  data: () => ({
    //
  }),
  components:{
    InstanceSecurityScore,
  }
};
</script>
