<template>
    <div class="login-form">
      <form @submit.prevent="validateForm">
        <div>
          <label for="email">Adresse e-mail:</label>
          <input type="email" id="email" v-model="email" @input="clearError" />
        </div>
        <div>
          <label for="password">Mot de passe:</label>
          <input type="password" id="password" v-model="password" @input="clearError" />
        </div>
        <div v-if="errorMessage" class="error-message">
          {{ errorMessage }}
        </div>
        <button type="submit">Se connecter</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        email: '',
        password: '',
        errorMessage: ''
      };
    },
    methods: {
      validateForm() {
        if (!this.isValidEmail(this.email)) {
          this.errorMessage = "L'adresse e-mail n'est pas au bon format.";
          return;
        }
        if (this.password.length < 6) {
          this.errorMessage = 'Le mot de passe doit contenir au moins 6 caractères.';
          return;
        }
        this.errorMessage = '';
        // Logique supplémentaire pour l'envoi des données au serveur ou autre
        alert('Formulaire envoyé avec succès!');
      },
      isValidEmail(email) {
        const emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$/;
        return emailPattern.test(email);
      },
      clearError() {
        this.errorMessage = '';
      }
    }
  };
  </script>
  
  <style scoped>
  .login-form {
    max-width: 300px;
    margin: 0 auto;
    padding: 1em;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  .login-form div {
    margin-bottom: 1em;
  }
  
  .login-form label {
    margin-bottom: .5em;
    color: #333333;
    display: block;
  }
  
  .login-form input {
    border: 1px solid #CCCCCC;
    padding: .5em;
    font-size: 1em;
    width: 100%;
    box-sizing: border-box;
  }
  
  .error-message {
    color: red;
    margin-bottom: 1em;
  }
  
  button {
    padding: 0.7em;
    color: #fff;
    background-color: #007BFF;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>