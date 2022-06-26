<template>
  <li>
    <h2>{{ name }}</h2>
    <button @click="toggleDetails">{{ detailsAreVisable ? 'Hide' : 'Show' }}</button>
    <ul v-if="detailsAreVisable">
      <li><strong>Phone:</strong> {{ phoneNumber }}</li>
      <li><strong>Email:</strong> {{ emailAddress }}</li>
    </ul>
  </li>
</template>


<script>
  export default {
    // props: [
    //   'name', 
    //   'phoneNumber', 'emailAddress'
    //   ],
    props: {
      name: {
        type: String,
        required: true
        },
      phoneNumber: {
        type: String, 
        required: true,
        },
      emailAddress: {
        type: String, 
        required: true,
      }
    },
    data() {
      return {
        detailsAreVisable: false,
        friend: {
          id: 'manuel',
          name: 'Manuel Lorenz',
          phone: '0123 45678 90',
          email: 'manuel@localhost.com',
        },
      }
    },
    methods: {
      toggleDetails() {
        this.detailsAreVisable = !this.detailsAreVisable;
      }
    }
  };
</script>