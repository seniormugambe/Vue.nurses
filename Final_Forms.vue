<template>
    
      <form @submit.prevent="submitForm">
        <!-- form fields here -->
        <label for="full_name">Full Name:</label>
        <input v-model="formData.full_name" type="text" id="full_name" />
      

      <div>
        <label for="email">Email:</label>
        <input v-model="formData.email" type="email" id="email" />
      </div>

      <div>
        <label for="password">Password:</label>
        <input v-model="formData.password" type="text" id="password" />
      </div>
      <label for="username">Username:</label>
        <input v-model="formData.username" type="text" id="username" />
      

      <div>
        <label for="partner_id">Partner ID:</label>
        <input v-model="formData.partner_id" type="text" id="partner_id" />
      </div>

      <div>
        <label for="phone_number">Phone Number:</label>
        <input v-model="formData.phone_number" type="text" id="phone_number" />
      </div>

      <label for="role">Role:</label>
        <input v-model="formData.role" type="text" id="role" />
      

      <div>
        <label for="roles">Roles:</label>
        <input v-model="formData.roles" type="text" id="roles" />
      </div>

      <div>
        <label for="sex">Sex:</label>
        <input v-model="formData.sex" type="text" id="sex" />
      </div>

      <div>
        <label for="status">Status:</label>
        <input v-model="formData.status" type="text" id="status" />
      </div>
        <button type="submit">Submit</button>
      </form>
    
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        formData: {
            full_name:'',
          username: '',
          email: '',
          password: '',
          partner_id :'',
          phone_number:'',
          role:"",
          roles:[],
          sex:"",
          status:""
        },
      };
    },
    methods: {
      async submitForm() {
        try {
          const headers = {
            'Content-Type': 'application/json',
            'User-Agent': 'insomnia/8.4.2',
            'admin_harsh':'d98926a4-b0a2-45d3-b764-589a270c7223'
          };
  
          const response = await axios.post('https://staging-api.teheca.com/api/v1/auth/register', this.formData, {
            headers: headers,
          });
  
          console.log('API response:', response.data);
        } catch (error) {
          console.error('Error submitting form:', error.message);
        }
      },
    },
  };
  </script>

	
