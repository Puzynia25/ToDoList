<template>
  <footer :todos="todos" class="text-sm text-gray-300 mt-10">
    {{ todos.length }} more to do, {{ filteredDone }} done
  </footer>
</template>

<script lang="ts">
import { Todo } from '~/types/Todo';

export default defineComponent({
  props: {
    todos: {
      type: Array as PropType<Todo[]>,
      required: true,
    },
  },
  computed: {
    filteredDone(): number {
      const result = this.todos.filter((todo) => todo.completed);
      return result.length;
    },
  },
});
</script>
