<template>
  <div>
    {{ titleConverted }} <br />
    <Table :columns="columns" :data="students" />
  </div>
</template>

<script>
import Table from "../components/Table";
export default {
  name: "Product",
  components: {
    Table,
  },
  data() {
    return {
      title: "Product Details",
      students: [],
      columns: [
        {
          label: "Id",
          field: "id",
        },
        {
          label: "Name",
          field: "name",
        },
        {
          label: "Price",
          field: "price",
        },
      ],
    };
  },
  mounted() {
    this.loadProduct();
  },
  methods: {
    loadProduct() {
      fetch("https://localhost:8089/product")
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