<template>
  <div>
    <p class="h1">Employer Assesments</p>
  </div>
  <div class="mt-6 justify-end max-w-md py-3 text-sm"> <button type="button"
  class="rounded-full bg-indigo-600 p-4 text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
    @click="open = true">Add assessment</button></div>
 
    <div
    class="block w-[800px] p-4 bg-white border border-gray-200 rounded-lg shadow bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:bg-gray-700 mt-2"
  >
    <collection-List :assessments=assessments></collection-List>
  </div>

  <TransitionRoot as="template" :show="open">
    <Dialog as="div" class="relative z-10" @close="open = false">
      <div class="fixed inset-0" />


      <div class="fixed inset-0 overflow-hidden">
        <div class="absolute inset-0 overflow-hidden">
          <div class="pointer-events-none fixed inset-y-0 right-0 flex max-w-full pl-10">
            <TransitionChild as="template" enter="transform transition ease-in-out duration-500 sm:duration-700"
              enter-from="translate-x-full" enter-to="translate-x-0"
              leave="transform transition ease-in-out duration-500 sm:duration-700" leave-from="translate-x-0"
              leave-to="translate-x-full">
              <DialogPanel class="pointer-events-auto w-screen max-w-md">
                <div class="flex flex-col overflow-y-scroll bg-white py-6 shadow-xl border">
                  <div class="px-4 sm:px-6">
                    <div class="flex items-start justify-between">
                      <DialogTitle class="text-base font-semibold leading-6 text-gray-900">Add Assesment</DialogTitle>
                      <div class="ml-3 flex h-7 items-center">
                        <button type="button"
                          class="rounded-md bg-white text-gray-400 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
                          @click="open = false">
                          <span class="sr-only">Close</span>
                          <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                        </button>
                      </div>
                    </div>
                  </div>
                  <div class="relative mt-6 flex-1 px-4 sm:px-6">
                    <collection-add @hide="closeModel" @addAssesment="saveApplication"></collection-add>
                  </div>
                </div>
              </DialogPanel>
            </TransitionChild>
          </div>
        </div>
      </div>
    </Dialog>
  </TransitionRoot>
</template>
<script setup lang="ts">
import { Menu, MenuButton, MenuItem, MenuItems, Dialog, DialogPanel, DialogTitle, TransitionChild, TransitionRoot } from "@headlessui/vue";
import { CodeBracketIcon, EllipsisVerticalIcon, FlagIcon, StarIcon } from "@heroicons/vue/20/solid";
import { XMarkIcon } from '@heroicons/vue/24/outline'
const open = ref(false)
let assessments = ref([])
// Get all assesment using useAuthLazyFetch
const getUrl = "https://v7-stark-db-orm.mercury.infinity-api.net/api/assessments/?offset=0&limit=100&sort_column=id&sort_direction=desc"
const { pending, data } = useAuthLazyFetch(getUrl, {});
if (data) assessments = data
// Save Application
const saveApplication = (newapplication: any) => {
  if (newapplication) {
    assessments.value.unshift(newapplication.value)
  }

}
// Close modal
const closeModel = (e: any) => {
  open.value = false;
  open.value = e;
};

</script>