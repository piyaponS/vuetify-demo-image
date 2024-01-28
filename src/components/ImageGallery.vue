<script setup>
     import { defineProps } from 'vue'

     const props = defineProps(["isColor"])
     const copyUrl = async (url) => {
          await navigator.clipboard.writeText(url)
     }
</script>

<template>
     <v-card class="mx-5 my-2 pa-3">
          <v-row>
               <v-col
               v-for="n in 200"
               cols="4"
               sm="3"
               lg="1">
                    <v-card>
                    <v-img 
                         :src="props.isColor === true ? `https://picsum.photos/500/300?image=${n * 4 + 10}`: `https://picsum.photos/500/300?image=${n * 4 + 10}&grayscale`"
                         aspect-ratio="1"
                         cover
                         @click="copyUrl(`https://picsum.photos/500/300?image=${n * 4 + 10}${props.isColor ? '' : '&grayscale'}`)"
                    >
                         <template v-slot:placeholder>
                              <v-row 
                                   class="fill-height ma-0"
                                   align="center"
                                   justify="center">
                                   <v-progress-circular
                                   color="grey-lighten-4"
                                        indeterminate
                                   >
                                   </v-progress-circular>
                              </v-row>
                         </template>
                    </v-img>
                    </v-card>
               </v-col>
          </v-row>
     </v-card>
</template>

