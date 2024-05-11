<template>
  <div id="chat-header">
    
    
    <ion-grid :fixed="true">
        <ion-row>
          <ion-col size="1"><p><</p></ion-col>
          <ion-col size="2">
              <ion-avatar>
                  <img alt="" src="https://ionicframework.com/docs/img/demos/avatar.svg" />
              </ion-avatar>
          </ion-col>
          <ion-col size="6">
              <div class="user-data">
                <p>{{name}}</p>
                <p class="smaller-p">tap here for contact info</p>
              </div>
          </ion-col>
          <ion-col>
            <p><ion-icon aria-hidden="true" :icon="videocam" /></p>
          </ion-col>
          <ion-col>
            <p><ion-icon aria-hidden="true" :icon="call" /></p>
          </ion-col>
        </ion-row>
    </ion-grid>
    
  </div>
</template>

<script setup lang="ts">
import { IonCol, IonGrid, IonRow, IonIcon, IonAvatar } from '@ionic/vue';
import { videocam, call } from 'ionicons/icons';

defineProps({
  name: String,
  pPic: String
});

</script>

<style scoped>
#chat-header {
  margin-top: 10%;
  height:10%;
  transform: translateY(-50%);
  border-top: red 1px solid;
  border-bottom: green 1px solid;
}

#chat-header ion-grid{
    margin-top: 1%;
}

.smaller-p{
    font-size:0.8em;
    line-height: 0.1em;
}
.user-data p{
  margin-top: 2%;
}

</style>