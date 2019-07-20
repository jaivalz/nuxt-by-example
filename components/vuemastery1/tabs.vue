<template>
  <div>
    <span
      v-for="(tab, index) in tabs"
      :key="index"
      class="tab"
      :class="{ activeTab: selectedTab === tab }"
      @click="selectedTab = tab"
      >{{ tab }}
    </span>
    <div v-show="selectedTab === 'Reviews'">
      <p v-if="!reviews.length">There are no reviews yet.</p>
      <ul v-else>
        <li v-for="(review, index) in reviews" :key="index">
          <p>{{ review.name }}</p>
          <p>Rating:{{ review.rating }}</p>
          <p>{{ review.review }}</p>
        </li>
      </ul>
    </div>

    <div v-show="selectedTab === 'Make a Review'">
      <product-review @review-submitted="addReview"></product-review>
    </div>
  </div>
</template>

<script>
import productReview from '@/components/vuemastery1/productReview.vue'

export default {
  components: {
    productReview
  },
  props: {
    reviews: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      tabs: ['Reviews', 'Make a Review'],
      selectedTab: 'Reviews'
    }
  },
  methods: {
    addReview(productReview) {
      this.reviews.push(productReview)
    }
  }
}
</script>

<style scoped>
.tab {
  margin-left: 20px;
  cursor: pointer;
}

.activeTab {
  color: #16c0b0;
  text-decoration: underline;
}

.outOfStock {
  text-decoration: line-through;
}
</style>
