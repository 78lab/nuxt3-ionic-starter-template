<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Index</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <h1>Index Page name: {{ user.savedName }}</h1>
      <InputEntry />
      <Auth />
      <h3>Time Ago: {{ timeAgo }}</h3>
      <ion-button @click="router.push('/about')">About</ion-button>
      <ion-button @click="router.push('/blank')">Blank</ion-button>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
definePageMeta({
  alias: ['/'],
})


const supabase = useSupabaseClient();
const user = useUserStore();
const startAt = Date.now();
const timeAgo = useTimeAgo(startAt);

const router = useIonRouter();
</script>
