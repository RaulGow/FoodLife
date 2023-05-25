<script setup lang="ts">
import { IonButtons, IonContent, IonHeader, IonMenuButton, IonPage, IonTitle, IonToolbar, IonInput, IonButton } from '@ionic/vue';
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const email = ref('');
const password = ref('');
const router = useRouter();

const validateForm = () => {
  if (email.value === '' || password.value === '') {
    alert('Por favor, ingresa todos los campos.');
  } else {
    // Realizar cualquier otra validación que necesites

    // Si los datos son correctos, puedes enviar el formulario
    console.log('Formulario enviado');
    setTimeout(() => {
        router.push('/folder/Prueba');
    }, 1000);
    
  }
};


const clearLogin = () => {
  email.value = '';
  password.value = '';
};

</script>
<template>
    <ion-page>
        <ion-header :translucent="true">
            <ion-toolbar>
                <ion-buttons slot="start">
                    <ion-menu-button color="primary"></ion-menu-button>
                </ion-buttons>
                <ion-title>Login</ion-title>
            </ion-toolbar>
        </ion-header>

        <ion-content :fullscreen="true">
            <ion-header collapse="condense">
                <ion-toolbar>
                    <ion-title size="large">Login</ion-title>
                </ion-toolbar>
            </ion-header>

            <div id="container">
                <form @submit.prevent="validateForm">
                    <ion-input v-model="email" label="Usuario o e-mail" label-placement="floating" fill="solid"
                        placeholder="example@email.com"></ion-input>
                    <br />
                    <ion-input v-model="password" label="Contraseña" label-placement="floating" fill="solid"
                        placeholder="password"></ion-input>
                    <br />
                    <div class="divButtons">
                        <ion-button color="danger" @click="clearLogin" fill="clear" shape="round">
                            Borrar
                        </ion-button>
                        <ion-button color="success" type="submit" fill="clear" shape="round">
                            Enviar
                        </ion-button>
                    </div>
                </form>

            </div>
        </ion-content>
    </ion-page>
</template>
<style scoped>
#container {
    margin: 1.5rem;
    /* text-align: center; */
    position: absolute;
    left: 0;
    right: 0;
    /* top: 50%;
    transform: translateY(-50%); */
}

.divButtons {
    text-align: right;
}

/* #container strong {
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
} */
</style>
  