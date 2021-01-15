<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Login</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <form @submit.prevent="onSubmit" novalidate>
        <ion-item style="margin-bottom: 20px;">
          <ion-label position="floating">
            Email
          </ion-label>
          <ion-input type="email" v-model="email"></ion-input>
        </ion-item>

        <ion-button expand="block" type="submit">
          Next
        </ion-button>
      </form>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonHeader, IonToolbar, IonContent, IonItem, IonLabel, IonButton } from '@ionic/vue';
import {useRouter} from 'vue-router'
import {ref} from 'vue'
export default  {
  name: 'Login',
  components: { IonHeader, IonToolbar, IonContent, IonPage,IonItem, IonLabel, IonButton  },
  setup(){
    const router = useRouter()
    const email = ref('')
    const onSubmit = () => {
      router.push(`/login-password`)
    }
    return {
      email,
      onSubmit
    }
  }
}
</script>