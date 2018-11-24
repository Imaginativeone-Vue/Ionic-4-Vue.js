<template>
  <ion-app>
    <ion-page class="show-page">
      <ion-header>
        <ion-toolbar>
          <ion-title>Ionic 4 + Vue A</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content class="content" padding>
          <ion-list>
            <ion-item v-for="user of users" v-bind:key="user.id">
              <ion-label full>{{user.name}}</ion-label>
            </ion-item>
          </ion-list>
          Hello 1
          <ion-tabs>
            <ion-tab>A</ion-tab>
          </ion-tabs>
      </ion-content>
      <ion-tabs>
        <ion-tab label="Location" icon="navigate" href="/tabs/(location:location)">
          <ion-router-outlet name="location"></ion-router-outlet>
        </ion-tab>
        <ion-tab label="My Details" icon="person" href="/tabs/(me:me)">
          <ion-router-outlet name="me"></ion-router-outlet>
        </ion-tab>
        <ion-tab label="Camp Details" icon="bookmarks" href="/tabs/(camp:camp)">
          <ion-router-outlet name="camp"></ion-router-outlet>
        </ion-tab>
      </ion-tabs>
    </ion-page>
  </ion-app>
</template>

<script>
import axios from 'axios';
export default {
  name: 'app',
  data () {
    return {
      users: []
    }
  },
  created() {
      axios.get('http://jsonplaceholder.typicode.com/users')
      .then(response => {
        this.users = response.data
      })
  }
}
</script>

<style>

</style>
