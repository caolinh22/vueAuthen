<template>
  <div>
    {{ titleConverted }} <br />
    <Table :columns="columns" :data="students" />
  </div>
</template>

<script>
import Table from "../components/Table";
export default {
  name: "Account",
  components: {
    Table,
  },
  data() {
    return {
      title: "Account Details",
      students: [],
      columns: [
        {
          label: "Id",
          field: "id",
        },
        {
          label: "User name",
          field: "username",
        },
        {
          label: "Full Name",
          field: "fullName",
        },
        {
          label: "Role",
          field: "role",
        },
        {
          label: "Status",
          field: "status",
        },
      ],
    };
  },
  mounted() {
    this.loadProduct();
  },
  methods: {
    loadProduct() {
      fetch("https://localhost:8089/account")
        .then((response) => response.json())
        .then((data) => (this.students = data));
    },
  },
  computed: {
    titleConverted() {
      return this.title.toUpperCase();
    },
  },
};
</script>

<style scoped>
.error {
  color: red;
}
</style>