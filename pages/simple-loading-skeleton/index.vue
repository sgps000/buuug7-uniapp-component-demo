<template>
   <view class="content">
      <view>单行</view>
      <simple-loading-skeleton v-if="hasMore"></simple-loading-skeleton>

      <view>多行</view>
      <view v-if="hasMore">
         <simple-loading-skeleton></simple-loading-skeleton>
         <simple-loading-skeleton></simple-loading-skeleton>
         <simple-loading-skeleton></simple-loading-skeleton>
         <simple-loading-skeleton></simple-loading-skeleton>
      </view>
   </view>
</template>

<script>
import SimpleLoadingSkeleton from "@buuug7/uniapp-components/lib/simple-loading-skeleton";
export default {
   components: {
      SimpleLoadingSkeleton
   },
   data() {
      return {
         hasMore: true
      };
   },

   mounted() {
      setTimeout(() => {
         this.hasMore = false;
      }, 3000);
   }
};
</script>

<style>
.content {
   margin: 1rem 0.5rem;
}
</style>
