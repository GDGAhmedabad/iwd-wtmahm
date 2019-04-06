<template>
    <v-container fluid class="mt-5"> 
        <v-layout wrap align-center justify-center row fill-height>
            <!-- <v-flex xs12 sm6 md3 class="mb-3">
                <v-img
                    :src="require('@/assets/img/svg/attendingfront.svg')"
                    :lazy-src="require('@/assets/img/svg/attendingfront.svg')"
                    width="80%">
                    <v-layout
                        slot="placeholder"
                        fill-height
                        align-center
                        justify-center
                        ma-0
                    >
                        <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-layout>
                </v-img>
            </v-flex> -->

            <v-flex xs12 sm12 md10 class="text--white" style="">
                <span class="pa-2 google-font mt-2" style="border-radius:8px;background-color:#E3F2FD;color:#0D47A1;font-size:150%">Attending</span>
                
                <p class="google-font mt-3 mb-0" style="font-size:150%;color:white">Join us at the {{data.eventVenue}}, on {{data.eventDate}}.</p>   
                
                <p class="google-font mt-2 " style="font-size:120%;color:white">On {{data.eventDate}} we’ll be taking technical sessions, hands-on demos, workshops, and some fun activities.</p>

                <!-- <v-btn :href="data.registrationLink" target="_blank" class="ma-0 google-font" color="white" style="text-transform: capitalize;border-radius:5px">Request for an Invitation</v-btn> -->

                <v-btn :href="data.eventMeetupLink" target="_blank" color="white" style="text-transform: capitalize;border-radius:5px"  class="ma-0 google-font" >Meetup</v-btn>
            </v-flex>       
       
        </v-layout>

    </v-container>
</template>

<script>
import homeData from '@/assets/data/home.json'

export default {
    data() {
        return {
            data: homeData
        }
    },
   
}
</script>
