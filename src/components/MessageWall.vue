
<template>
    <div id="message-wall">
        <ion-grid>
            <ion-row :key="msg.id" v-for="msg in messages">
                {{console.log('looping ' + msg.id)}}
                <ion-col size="10">
                        <p v-bind:class="sentByMe(msg.from, user.id)?'left-msg':'right-msg'">{{msg.textContent}}</p>
                        <p v-bind:class="sentByMe(msg.from, user.id)?'left-msg':'right-msg'">{{formattedDate(msg.datetimelog)}}</p>
                </ion-col>
            </ion-row>
        </ion-grid>
    </div>
  </template>
  
  <script setup lang="ts">
    import { IonCol, IonGrid, IonRow } from '@ionic/vue';
    const props = defineProps({
      messages: {
        type: Array
      },
      user: {
        type: Object
      },
    });
  </script>
 
  <script lang="ts">
    export default {
        methods: {
            sentByMe( pIdSender: number, pOwnUserID: number ) {
                const flag = ( pIdSender === pOwnUserID )? true : false;
                return flag;
            },
            formattedDate( pTimeStamp: number ) {
                const date = new Date(pTimeStamp);
                const hours = date.getHours() % 12; // Convert to 12-hour format (0-11)
                const minutes = date.getMinutes().toString().padStart(2, '0'); // Add leading zero for single-digit minutes
                const ampm = date.getHours() >= 12 ? 'PM' : 'AM';
                return `${hours}:${minutes} ${ampm}`;
            }
        },
    };
  </script>
  
  <style scoped>
    #message-wall {
      margin-top:-9%;
      height:78%;
      border-top: rgb(47, 47, 37) 1px solid;
      width:100%;
      margin-left: 5%;
      /*border-bottom: blue 1px solid;*/
    }
    .left-msg{
      text-align: left;
    }
    .right-msg{
      text-align: right;
    }
  </style>