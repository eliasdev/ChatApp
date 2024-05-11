<template>
    <div id="typer">
      <ion-grid :fixed="true">
        <ion-row>
          <ion-col size="1"><p>+</p></ion-col>
          <ion-col size="8.5">
            <ion-input class="replier" @keyup.enter="sender" placeholder=""></ion-input>
          </ion-col>
          <ion-col>
            <p><ion-icon aria-hidden="true" :icon="camera" /></p>
          </ion-col>
          <ion-col>
            <p><ion-icon aria-hidden="true" :icon="mic" /></p>
          </ion-col>
        </ion-row>
    </ion-grid>
    </div>
    
</template>
  
  <script setup lang="ts">
    import { IonCol, IonGrid, IonRow, IonIcon, IonInput } from '@ionic/vue';
    import { camera, mic } from 'ionicons/icons';

    const sender = (event: { target: { value: any; }; }) => {
      // Access the entered text from the event object
      const enteredText = event.target.value;
      console.log("Enter pressed:", );
    };


  </script>
  
  <style scoped>
  #typer {
    text-align: center;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 6%;
    height:10%;
    border-top: orange 1px solid;
    border-bottom: cyan 1px solid;
    background-color: rgb(19, 19, 19);
  }
  #typer p{
    font-size: 1.3em;
  }
  .replier{
    margin-top: 5%;
    background-color: rgb(57, 57, 57);
    border-radius: 25px;
    text-align: left;
    padding: 0 10px 0 10px !important;
  }
  .transparent-bg{
    background: transparent !important;
  }
  </style>
  