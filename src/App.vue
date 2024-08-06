<template>
    <div class="contact-form">
      <h1>Contactez-nous</h1>
      
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">Nom</label>
          <input type="text" id="name" v-model="name" placeholder="Nom" required />
        </div>
  
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" v-model="email" placeholder="Email" required />
        </div>
  
        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" v-model="message" placeholder="Ecrire un message" rows="5" required></textarea>
        </div>
  
        <button type="submit">Envoyer</button>
      </form>
  
      <div v-if="submitted" class="success-message">
        Merci pour votre message, {{ name }}. Nous vous répondrons bientôt à l'adresse {{ email }}.
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  
  const name = ref('');
  const email = ref('');
  const message = ref('');
  const submitted = ref(false);
  
  
  function submitForm() {

    console.log(`Nom: ${name.value}`);
    console.log(`Email: ${email.value}`);
    console.log(`Message: ${message.value}`);
    
    
    submitted.value = true;
  

    name.value = '';
    email.value = '';
    message.value = '';
  }
  </script>
  
  <style scoped>

  .contact-form {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  

  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    font-weight: bold;
    display: block;
    margin-bottom: 5px;
  }
  
  input, textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
  }
  
  button {
    background-color: #007BFF;
    color: white;
    padding: 10px 15px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
    width: 100%;
  }
  
  button:hover {
    background-color: #0056b3;
  }

  .success-message {
    margin-top: 20px;
    padding: 10px;
    background-color: #d4edda;
    color: #155724;
    border: 1px solid #c3e6cb;
    border-radius: 4px;
  }
  </style>
  