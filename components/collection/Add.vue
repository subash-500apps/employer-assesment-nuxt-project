<template>
    <div>
        <!--Add required fields-->
        <div class="mt-2">
        <input placeholder=" Name" v-model="name" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
          <div class="mt-2">
        <input placeholder=" Max time allowed" v-model="max_time_allowed" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>

   
      <div class="mt-2">
        <input placeholder=" Difficulty level" v-model="difficulty_level" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
     <div class="mt-2">
        <input placeholder=" Multiple attemps allowed" v-model="multiple_attempts_allowed" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
     <div class="mt-2">
        <input placeholder=" Status" v-model="status" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
  
      <div class="mt-2">
        <input placeholder=" Description" v-model="description" type="text" name="email" id="email"
          class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class="mt-5 sm:mt-6 sm:grid sm:grid-flow-row-dense sm:grid-cols-2 sm:gap-3">
      <button type="button"
        class="inline-flex w-full justify-center rounded-md bg-gray-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600 sm:col-start-2"
        @click="saveTask(false)">
        Apply
      </button>

      <button type="button"
        class="mt-3 inline-flex w-full justify-center rounded-md bg-white px-3 py-2 text-sm font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50 sm:col-start-1 sm:mt-0"
        @click="closeModal(false)">
        Cancel
      </button>
    </div>
    </div>
</template>
<script setup>
let {name,max_time_allowed,difficulty_level,description,multiple_attempts_allowed,status}=ref("")
const url="https://v7-stark-db-orm.mercury.infinity-api.net/api/assessments/"
const emit = defineEmits(["hide", 'addAssesment']);
const saveTask = async (close) => {
  // Emit event for closing the modal
  emit("hide", close);
  // Add application using useAuthLazyFetchPost
  const { data } = await useAuthLazyFetchPost(`${url}`, {
    body: {
     name: name?name:"",
  type: "employer",
  max_time_allowed: max_time_allowed?max_time_allowed:"",
  due_date: "2023-04-08T05:47:41.777Z",
  difficulty_level: difficulty_level?difficulty_level:"",
  description: description?description:"",
  questions: {},
  multiple_attempts_allowed: multiple_attempts_allowed?multiple_attempts_allowed:"",
  instructions: {},
  status: status?status:"",
  owner_id: "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  last_modified_date: "2023-04-08T05:47:41.777Z"
}
    })
  // Emit event for adding application
if(data)  emit("addAssesment", data);
};
  // Close modal
  const closeModal = (close) => {
  emit("hide", close);
};
</script>