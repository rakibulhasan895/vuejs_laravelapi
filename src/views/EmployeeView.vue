<template>
  <div class="card">
    <div class="card-header">
      <h4>
      <Routerlink to="#" class="btn btn-danger"> Create Employee</Routerlink>
      </h4>
     </div>
     <div class="card-body">
      <table class="table table-bodered">
        <thead>
          <th>SL</th>
          <th> Name </th>
          <th>Email </th>
          <th> Phone</th>
          <th>Address</th>
          <th>test</th>

        </thead>
        <tbody>
          <tr class="td" v-for = "(Employee,index) in this.employees" key = "index"></tr>

          

          

        </tbody>
        

      </table>

     </div>
  </div>
</template>

<!-- <script >
  import axios from 'axios'
  export default(){
    name:'employees',
    data(){
      return {
        employess:[]
      },
      mounted(){
      this.getEmployees();
      },
      method:{
        getEmployees(){
          axios.get('http://127.0.0.1:8000/api/deparments').then(res =>{
            this.employess = res.data.employess
          console.log(res);
          })
        }
      },
    }
  }

</script> -->