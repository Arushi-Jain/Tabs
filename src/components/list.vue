<template>
    <q-table
    title="Table Title"
    :data="mapToTable()"
    :columns="columns"
    row-key="name"
  />
</template>

<script>
export default {
  data () {
    return {
      tableData: [],
      columns: [{
        name: 'id',
        required: true,
        label: 'Id',
        align: 'left',
        field: 'id',
        sortable: true,
        classes: 'my-class',
        style: 'width: 500px'
      }, {
        name: 'Post Id',
        required: true,
        label: 'Post Id',
        align: 'left',
        field: 'postId',
        sortable: true,
        classes: 'my-class',
        style: 'width: 500px'
      }, {
        name: 'name',
        required: true,
        label: 'Name',
        align: 'left',
        field: 'name',
        sortable: true,
        classes: 'my-class',
        style: 'width: 500px'
      }, {
        name: 'email',
        required: true,
        label: 'Email',
        align: 'left',
        field: 'email',
        sortable: true,
        classes: 'my-class',
        style: 'width: 500px'
      }]
    }
  },
  props: {
    list: {
      type: Array,
      required: true
    }
  },
  methods: {
    mapToTable () {
      return this.list
    }
  }
}
</script>

<style>

</style>
