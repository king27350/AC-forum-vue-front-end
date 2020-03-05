<template>
  <div class="card">
    <div class="card-header">
      <strong>{{Comments.length}}</strong> 已評論餐廳
    </div>
    <div class="card-body">
      <router-link
        v-for="Comment in Comments "
        :key="Comment.id"
        :to="{ name: 'restaurant', params: { id: Comment.id } }"
      >
        <img :src="Comment.Restaurant.image" width="60" height="60" class="avatar m-1" />
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    Comments: {
      type: Array,
      required: true
    }
  }
};
</script>