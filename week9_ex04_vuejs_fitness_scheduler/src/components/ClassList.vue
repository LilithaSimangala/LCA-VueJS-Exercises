<template>
  <div>
    <ClassCard
      v-for="(item, index) in classes"
      :key="index"
      :classItem="item"
      @delete="$emit('delete', index)"
    />
  </div>
</template>

<script>
import ClassCard from './ClassCard.vue'

export default {
  components: {
    ClassCard
  },
  props: {
    classes: Array
  }
}
</script>