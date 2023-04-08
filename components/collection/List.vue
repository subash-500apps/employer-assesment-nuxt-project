<template>
  <table class="min-w-full divide-y divide-gray-700">
    <thead>
      <tr>
        <th scope="col" class="py-3 5 pl-4 pr-3 text-left text-sm font-semibold sm:pl-0 group">
          Details
        </th>
      </tr>
    </thead>
    <tbody class="divide-y divide-gray-800">
      <tr v-for="(assessment, index) in props.assessments" :key="index" class="cursor-pointer hover:bg-gray-200">
        <td class="py-4 pl-4 pr-3 text-sm font-medium sm:pl-0">
          <span>Candidate name - {{ assessment.name }}</span>
          <p>Type - {{ assessment.type }}</p>
          <p>Difficulty level - {{ assessment.difficulty_level }}</p>
          <p>Max time - {{ assessment.max_time_allowed }}</p>
          <p>Due time - {{ assessment.due_date }}</p>
          <p>Max attempts allowed - {{ assessment.multiple_attempts_allowed }}</p>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script setup >
// Define props
const props = defineProps({
  assessments: Array,
});

</script>