<template><div class="container space y-8 mt-5">
      <div v-for="assessment in assessments" :key="assessment">
    <p class="h2">Exam name - {{ assessment.name }}</p>
    <p class="h2">Type - {{ assessment.type }}</p>
    <p class="h2">Max time - {{ assessment.max_time_allowed }}</p>
    <p class="h2">Due time - {{ assessment.due_date }}</p>
    <hr v-if="assessments.length > 1" class="border space-y-8 mt-5" />
    </div>
    
</div></template>

<script setup lang="ts">
const getUrl="https://v7-stark-db-orm.mercury.infinity-api.net/api/assessments/?offset=0&limit=100&sort_column=id&sort_direction=desc"
const { pending, data: assessments } = useAuthLazyFetch(getUrl, {});
</script>