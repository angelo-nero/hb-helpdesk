<template>
  <div class="flex items-center gap-2">
    <Avatar :label="user.name" :image="user.user_image" v-bind="$attrs" />
  </div>
</template>
<script setup lang="ts">
import { Avatar } from "frappe-ui";
import { useUserStore } from "@/stores/user";
const userStore = useUserStore();

const props = defineProps({
  name: {
    type: String,
    required: true,
  },
});
const user = userStore.getUser(props.name);
</script>
