<template>
    <div>
        <div class="mt-2">
        <input placeholder=" Name" v-model="name" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-2">
        <input placeholder=" Type" v-model="type" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-2">
        <input placeholder=" Max time allowed" v-model="max_time_allowed" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>

      <div class="mt-2">
        <input placeholder=" Due date" v-model="due_date" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-2">
        <input placeholder=" Difficulty level" v-model="difficulty_level" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-2">
        <input placeholder=" Description" v-model="description" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-2">
        <input placeholder=" Questions" v-model="questions" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div><div class="mt-2">
        <input placeholder=" Multiple attemps allowed" v-model="multiple_attempts_allowed" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-2">
        <input placeholder=" Instructions" v-model="instructions" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div><div class="mt-2">
        <input placeholder=" Status" v-model="status" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-2">
        <input placeholder=" Owner ID" v-model="owner_id" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-2">
        <input placeholder=" Last Modifed date" v-model="last_modified_date" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      

    </div>
</template>
<script setup>
const {name,type,max_time_allowed,due_date,difficulty_level,description,questions,multiple_attempts_allowed,instructions,status,owner_id,last_modified_date}=ref("")
</script>