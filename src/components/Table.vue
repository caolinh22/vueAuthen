<template>
  <table>
    <thead>
      <tr>
        {{
          data.length
        }}
        <button @click="increase()">Increase Number</button>
      </tr>
      <tr>
        <th v-for="col in columns" :key="col.field">{{ col.label }}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in data" :key="item.label">
        <td v-for="col in columns" :key="col.field">
          <template v-if="col.field !== 'action'">
            {{ item[col.field] }}
          </template>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  methods: {
    test(props) {
      console.log(props);
    },
  },
  props: {
    data: {
      type: Array,
      default: () => [],
    },
    columns: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    increaseLength() {
      this.$emit("increase");
    },
  },
};
</script>

<style scoped>
</style>