<template>
  <v-simple-table dark>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">
            ID
          </th>
          <th class="text-left">
            Title
          </th>
          <th class="text-left">
            isDone?
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in todoList"
          :key="item.id"
        >
          <td>{{ item.id }}</td>
          <td>{{ item.title }}</td>
          <td>{{ item.isDone }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
import gql from 'graphql-tag'

export default {
    apollo: {
        todoList: gql`
            query allTodoQuery {
                todoList {
                    id
                    isDone
                    title
                    userId
                }
            }
        `
    }
}
</script>

<style>

</style>