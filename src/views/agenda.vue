<template>
    <v-slide-y-reverse-transition>
    <v-container class="pa-0 mt-5" fluid v-show="show" >
        <v-layout wrap align-center justify-center row >

            <v-flex xs12>
                <v-img :src="imgPath.src" class="elevation-1 hidden-sm-and-up">
                    <v-layout
                        align-end
                        fill-height 
                        pa-3
                        white--text
                        style="background-image: linear-gradient(transparent, #212121);"
                    >
                        <div class="google-font font-weight-light" style="font-size:200%">Agenda</div>
                    </v-layout>
                </v-img>
            </v-flex>

            <v-flex xs12 md9 sm10 lg10 class="pa-0 mt-5 hidden-sm-and-down">
                <span class="pa-2 google-font" style="border-radius:8px;background-color:#d1c4e9;color:#311b92;font-size:150%">Agenda</span>
                <br><br>
                <p class="google-font" style="font-size:120%">Hone your skills. Ask technical questions. Get inspired. This year’s program is packed with breakouts, keynotes, spotlights, panels, and bootcamps.
                <br>
                Check back often as we continue to add new sessions.</p>
            </v-flex>

        <!-- grey lighten-5 -->
            <v-flex xs12 md12 sm12 lg12 class="pa-0 elevation-0">
                <v-layout wrap align-center justify-center row  >
                    <v-flex xs12 md10>
                <v-tabs
                    v-model="active" 
                    color="rgb(249, 249, 249)"
                    slider-color="indigo">
                    <v-tab ripple style="text-transform: capitalize;"  >
                        Sessions
                    </v-tab>

                    <v-tab-item>
                        <v-card flat>
                            <v-card-text>
                                <v-layout justify-start row fill-height wrap>
                                    
                                    <v-flex xs12 sm4 md3 lg3 class="pa-2" v-for="(item,i) in sessions" :key="i">
                                        <v-card class="elevation-0" style="border: 1px solid rgb(224, 224, 224);min-height:280px;border-radius:5px">
                                            <v-card-title primary-title>
                                            <div>
                                                <p class="mb-0 google-font" style="font-size:130%;color:#424242">{{item.title}}</p>
                                                <v-chip v-if="item.track.length>0" label small class="ma-0 my-1" outline :color="showColor(item.track)">
                                                    <v-icon small left>{{showIcon(item.track)}}</v-icon>
                                                    {{item.track}}
                                                </v-chip>
                                                <div class="google-font" style="font-size:110%">{{item.des}}</div>
                                            </div>
                                            </v-card-title>
                                        </v-card>
                                    </v-flex>

                                </v-layout>
                            </v-card-text>
                        </v-card>
                    </v-tab-item>

                    <v-tab ripple style="text-transform: capitalize;" >
                        Schedule
                    </v-tab>
                    <v-tab-item>
                        <v-card flat>
                            <v-card-text>
                                <v-container style="max-width: 900px;">
                                    
                                    <v-timeline
                                        align-top
                                        dense
                                        v-for="(item,i) in scheduleData" :key="i"
                                        class=""
                                    >
                                        <v-timeline-item
                                            :color="showColor(item.tag)"
                                            small 
                                        >
                                            <v-layout pt-3>
                                                <v-flex xs3>
                                                    <strong class="google-font">{{item.startTime}}</strong>
                                                </v-flex>
                                                <v-flex xs9>
                                                    <strong class="google-font">{{item.topic}}</strong>
                                                    <div class="caption">
                                                        <v-chip v-if="item.tag.length>0" label small class="ma-0" outline :color="showColor(item.tag)">
                                                            <v-icon small left>{{showIcon(item.tag)}}</v-icon>
                                                            {{item.tag}}
                                                        </v-chip>
                                                    </div>
                                                    <div class="google-font">{{item.des}}</div>
                                                </v-flex>
                                            </v-layout>
                                        </v-timeline-item>

                                    </v-timeline>

                                </v-container>
                            </v-card-text>
                        </v-card>
                    </v-tab-item>
                </v-tabs>
                </v-flex>
                </v-layout>
            </v-flex>

        </v-layout>
    </v-container>
    </v-slide-y-reverse-transition>
</template>

<script>

import data from '@/assets/data/sessions.json'
import scheduledata from '@/assets/data/schedule.json'
export default {
    data() {
        return {
            show:false,
            imgPath:{
                src: require('@/assets/img/bg.jpg')
                },
            active: null,
            sessions:data,
            scheduleData:scheduledata,
            items: [
            'Projects', 'Talks', 'Blogs'
            ],
            model: 'tab-2',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        }
    },
    methods:{
        showColor(tag){
            if(tag == "Workshop"){
                return "red"
            }
            else if(tag == "Product Demo"){
                return "green"
            }
            else if(tag == "Personal Branding"){
                return "#4a148c"
            }
            else if(tag == "Fun"){
                return "#9e9d24"
            }
            else if(tag == "Cloud"){
                return "orange"
            }
            else if(tag == "Design"){
                return "brown"
            }
            else if(tag == "Flutter"){
                return "#03a9f4"
            }
        },
        showIcon(tag){
            if(tag == "Workshop"){
                return "code"
            }
            else if(tag == "Product Demo"){
                return "stay_primary_portrait"
            }
            else if(tag == "Personal Branding"){
                return "trending_up"
            }
            else if(tag == "Fun"){
                return "thumbs_up_down"
            }
            else if(tag == "Cloud"){
                return "cloud"
            }
            else if(tag == "Design"){
                return "format_paint"
            }
            else if(tag == "Flutter"){
                return "laptop"
            }
        }
    },
    mounted(){
        this.show = true
    }
}
</script>



