<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Chats</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <div v-if="isMobile">
        <ChatHeader name="Manolo Arguedas" pPic="https://ionicframework.com/docs/img/demos/avatar.svg" />
        <MessageWall v-bind:messages="messages" :user="user"></MessageWall>
        <ChatTyper @onSentMessage="addAndRender" :user="user"></ChatTyper>
      </div>
      <div v-if="!isMobile"><ExploreContainer name="Please switch to mobile view & reload" /></div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, isPlatform } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';
import ChatHeader from '@/components/ChatHeader.vue';
import MessageWall from '@/components/MessageWall.vue';
import ChatTyper from '@/components/ChatTyper.vue';
</script>

<script lang="ts">
  const addAndRender = (pMessage:any) => {
      console.log(messages.length);
      messages.push(pMessage);
      console.log(messages.length);
  }
  const isMobile = isPlatform('mobile')
  const user = {
    id: 123,
    username: "eliasdev",
    roleID: 3
  };

  let messages = [
  {
    id:324,
    from:1,
    to:2,
    textContent:"this is a message",
    datetimelog:1715401402671
  },
  {
    id:2134,
    from:123,
    to:2,
    textContent:"this is a SECOND message",
    datetimelog:1715401402671
  },
  {
    id:3224,
    from:1,
    to:2,
    textContent:"this is THIRD a message",
    datetimelog:1715401402671
  },
];
</script>