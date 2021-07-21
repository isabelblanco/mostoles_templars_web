<template>
<div class="v-application" v-if="this.dataContent && this.dataContent.TEXTOS">
  <in-construction :content='dataContent'></in-construction>
</div>
</template>

<script>
  import firebase from "firebase/app";
  import "firebase/analytics";
  import "firebase/auth";
  import "firebase/firestore";
  import in_construction from '../components/in_construction.vue'

  export default {
    components: {
      name: "in-dd",
      in_construction
    },
    data: function() {
      return {
        dataContent: {},
      }
    },
    mounted: function() {
      const config = {
        apiKey: "AIzaSyBGksiQGKDQ1jM5jTf7AEN_wf54Sdp3gJU",
        authDomain: "mostolestemplarsweb.firebaseapp.com",
        databaseURL: "https://mostolestemplarsweb-default-rtdb.europe-west1.firebasedatabase.app",
        projectId: "mostolestemplarsweb",
        storageBucket: "mostolestemplarsweb.appspot.com",
        messagingSenderId: "949832789348",
        appId: "1:949832789348:web:ffd8e309642531be3a5e71",
        measurementId: "G-G69DCC48LP"
      }

      if (!firebase.apps.length) {  
        firebase.initializeApp(config)
      }
      let info = {}
      const db = firebase.firestore();
      db.collection("CONTENT")
        .get()
        .then((data) => {
          data.forEach((doc) => {
            info[doc.id] = doc.data();
          });
          this.dataContent = info;
        }
      );
    }
  }
</script>