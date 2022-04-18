<template>
  <div>
    <ul class="list-group list-group-flush">
      <li class="list-group-item my-2" v-for="(item, i) in items" :key="i">
        {{ item }}
        <button class="btn btn-danger btn-sm" @click="removeTask(i)">
          Borrar
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TaskList",
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    removeTask(index) {
      this.$emit("click", index);
    },
  },
};
</script>

<style lang="scss" scoped></style>
