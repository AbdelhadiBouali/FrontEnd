<template>
  <section>
  <h1>Choisissez l'une des deux fonctionalités suivantes </h1>
  <form class="cf" action="./ajouter">
   
 
 
    <input type="submit" value="Ajouter Enseignant" id="input-submit">
    
  </form>
  <form class="cf" action="./importer">
    <input type="submit" value="Importer piece jointe" id="input-submit">
     </form>
      <form class="cf" action="./afficher_enseignant">
    <input type="submit" value="Afficher les enseignants" id="input-submit">
     </form>
      <form class="cf" action="./afficher_file">
    <input type="submit" value="Afficher les piece jointes" id="input-submit">
     </form>
  </section>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      user: {
        firstname: "",
        lastname: "",
        phone: ""
      }
    };
  },
  methods: {
    handleSubmit() {
      axios.post("/submit", this.$data).then(() => {
        this.$data.user = {};
      });
    }
  }
};
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Merriweather);
*,
*:before,
*:after {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

html,
body {
  background: #f1f1f1;
  font-family: "Merriweather", sans-serif;
  padding: 1em;
}

h1 {
  text-align: center;
  color: #a8a8a8;
  text-shadow: 1px 1px 0 white;
}

form {
  max-width: 600px;
  text-align: center;
  margin: 20px auto;
}
form input,
form textarea {
  border: 0;
  outline: 0;
  padding: 1em;
  -moz-border-radius: 8px;
  -webkit-border-radius: 8px;
  border-radius: 8px;
  display: block;
  width: 100%;
  margin-top: 1em;
  font-family: "Merriweather", sans-serif;
  -moz-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
  resize: none;
}
form input:focus,
form textarea:focus {
  -moz-box-shadow: 0 0px 2px #e74c3c !important;
  -webkit-box-shadow: 0 0px 2px #e74c3c !important;
  box-shadow: 0 0px 2px #e74c3c !important;
}
form #input-submit {
    margin-top: 100px;
  color: white;
  background: #f6921e;
  cursor: pointer;
}

form #input-submit:hover {
  -moz-box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
  -webkit-box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
  box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
}
form textarea {
  height: 126px;
}



@media (max-width: 480px) {
  .half {
    width: 100%;
    float: none;
    margin-bottom: 0;
  }
}

</style>
