<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <ion-button id="open-modal">Open Datetime Modal</ion-button>
      <ion-modal trigger="open-modal" :show-backdrop="false">
        <ion-content>
          <ion-datetime></ion-datetime>
        </ion-content>
      </ion-modal>

      <ion-button @click="openModal">Open Datetime Modal 2</ion-button>
      <ion-modal :is-open="isModalOpen" :show-backdrop="false">
        <ion-content>
          <ion-datetime></ion-datetime>
        </ion-content>
      </ion-modal>

    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton, IonModal, IonDatetime } from '@ionic/vue';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'HomePage',
  components: { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton, IonModal, IonDatetime },
  setup() {
    const isModalOpen = ref(false);
    const openModal = () => isModalOpen.value = true;

    return { isModalOpen, openModal };
  }
});
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>