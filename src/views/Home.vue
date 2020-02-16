<template>
  <v-slide-y-reverse-transition>
    <v-content class="pa-0" v-show="show">

      <v-container fluid class="pa-0 mt-5 hidden-sm-and-down">
        <v-layout wrap align-center justify-center row fill-height class="">
          <v-flex xs12 md10 >
            <startscreen/>
          </v-flex>
        </v-layout>
      </v-container>

      <v-container fluid class="pa-0 mt-5 hidden-sm-and-up"  >
        <v-layout wrap align-center justify-center row fill-height class="">
          <v-flex xs12 md10 >
            <startscreenMobile/>
          </v-flex>
        </v-layout>
      </v-container>

      <v-container fluid class="pa-0">
        <v-layout wrap align-center justify-center row fill-height class="">
          <v-flex xs12 md10 >
            <stats/>
          </v-flex>
        </v-layout>
      </v-container>

      <v-container fluid class="pa-0 py-3" :style="{'background-image':'url('+require('@/assets/img/svg/a.svg')+')'}" style="background-size:3000px">
        <v-layout wrap align-center justify-center row fill-height class="">
          <v-flex xs12 md10 >
            <homespeaker/>
            <featureListing/>
            <partners/>
          </v-flex>
        </v-layout>
      </v-container>

    </v-content>

  </v-slide-y-reverse-transition>
</template>

<script>
  import startscreen from '../components/home/startscreen'
  import stats from '../components/home/stats'
  import homespeaker from '../components/home/home-speakers'
  import featureListing from '../components/home/features-content'
  import partners from '../components/partners'
  import startscreenMobile from '../components/home/startscreenMobile'


  export default {
    components: {
      startscreen,  
      stats,
      homespeaker,
      partners,
      featureListing,
      startscreenMobile
    },
    data(){
      return{
        show:false
      }
    },
    created(){
      this.show = true
    }
  }
</script>
