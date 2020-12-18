<template>
  <div class="about">
    <h1>This is an home page</h1>
    <table class="table ">
      <thead>
        <tr>
          <th>name</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="userData in userDatas" :key="userData.id">
          <td>{{userData.name}}</td>
        </tr>
      </tbody>
    </table>
    
  </div>
</template>

<script>
  import axios from 'axios';

export default {

  created() {
            this.indexUserSocieteList();
        },
        data() {
            return {
                userDatas: {},
            };
        },
        methods: {
          indexUserSocieteList() {
                axios.get("http://laboratoireainitti.ma/indexUserSocieteList").then(({ data }) => (this.userDatas = data));
            },
        }
}
</script>
