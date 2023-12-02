<template>
  <div class="card">

    <div class="card-body">
      <table class="table table-bordered">
        <thead>
          <th>SL</th>
          <th>Name</th>
          <th>Email</th>
          <th>Phone</th>
          <th>Address</th>
        </thead>                                              
            <tbody class="bg-white divide-y divide-gray-200 divide-solid">
                <tr v-for ="employee in data" :key="index"> 
                    <td class="px-6 py-4 whitespace-no-wrap text-sm leading-5 text-gray-900">
                        {{ employee.id }}
                    </td>
                    <td class="px-6 py-4 whitespace-no-wrap text-sm leading-5 text-gray-900">
                        {{ employee.name }}
                    </td>
                    <td class="px-6 py-4 whitespace-no-wrap text-sm leading-5 text-gray-900">
                        {{ employee.email }}
                    </td>
                    <td class="px-6 py-4 whitespace-no-wrap text-sm leading-5 text-gray-900">
                        {{ employee.phone }}
                    </td>
                    <td class="px-6 py-4 whitespace-no-wrap text-sm leading-5 text-gray-900">
                        {{ employee.address }}
                    </td>
                </tr> 
            </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      data: [],
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
  fetchData() {
  axios.get('http://127.0.0.1:8000/api/employees')
    .then(response => {
      this.data = response.data.data;
      console.log(this.data); // Log the response

    })
    .catch(error => {
      console.error('Error fetching data:', error);
      this.message = 'Error fetching data';
    });
},
  },
};
</script>
