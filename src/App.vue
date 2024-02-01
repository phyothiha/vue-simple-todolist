<script setup>
import { ref } from "vue";

const newTask = ref("");

const handleTaskCreate = async () => {
  try {
    const res = await fetch("http://127.0.0.1:7000/api/tasks", {
      method: "POST",
      headers: {
        Accept: "application/json",
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        name: newTask.value,
      }),
    });

    if (res.ok) {
      console.log(res);
    } else {
      console.error(res);
    }
  } catch (err) {
    console.error(err);
  }
};
</script>

<template>
  <div class="h-screen bg-slate-200 flex items-center justify-center">
    <div class="md:w-8/12 2xl:w-5/12 bg-white rounded-md shadow-lg">
      <!-- card text -->
      <div class="p-8 pb-0">
        <h1 className="text-2xl font-medium text-center">
          Vue 3.x Simple TodoList
        </h1>

        <div class="mt-8 flex justify-center gap-4">
          <div class="w-6/12">
            <input
              type="text"
              class="block w-full rounded-md border-0 py-2 px-4 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 text-xs leading-6"
              placeholder="Add new task"
              v-model="newTask"
            />
            <div class="text-xs text-slate-400 italic mt-2">
              Task name should be more than 5 characters.
            </div>
          </div>
          <button
            class="text-xs tracking-wide h-[40px] shadow bg-indigo-100 px-4 rounded font-bold hover:bg-indigo-200 transition ease-in-out duration-300"
            @click="handleTaskCreate"
          >
            Create
          </button>
        </div>

        <div class="mt-8 space-y-4">
          <!-- rows -->
          <div class="grid grid-cols-12">
            <div class="col-span-10 pr-8">
              <div class="flex gap-4 items-start">
                <input
                  type="checkbox"
                  class="rounded checked:ring-indigo-500"
                />
                <div class="text-sm leading-relaxed">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Doloremque, impedit accusamus! Magni cum maiores tempora alias
                  unde saepe, temporibus eaque doloremque, nobis deserunt
                  commodi blanditiis quod tempore aspernatur. Similique,
                  facilis.
                </div>
              </div>
            </div>

            <div class="col-span-2">
              <div class="flex gap-2 justify-end">
                <button
                  class="border border-blue-200 px-4 py-2 rounded hover:bg-blue-300 transition ease-in-out duration-300"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="16"
                    height="16"
                    viewBox="0 0 24 24"
                  >
                    <path
                      fill="currentColor"
                      d="M5 21q-.825 0-1.412-.587T3 19V5q0-.825.588-1.412T5 3h8.925l-2 2H5v14h14v-6.95l2-2V19q0 .825-.587 1.413T19 21zm4-6v-4.25l9.175-9.175q.3-.3.675-.45t.75-.15q.4 0 .763.15t.662.45L22.425 3q.275.3.425.663T23 4.4q0 .375-.137.738t-.438.662L13.25 15zM21.025 4.4l-1.4-1.4zM11 13h1.4l5.8-5.8l-.7-.7l-.725-.7L11 11.575zm6.5-6.5l-.725-.7zl.7.7z"
                    />
                  </svg>
                </button>

                <button
                  class="border border-rose-200 px-4 py-2 rounded hover:bg-rose-300 transition ease-in-out duration-300"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="16"
                    height="16"
                    viewBox="0 0 24 24"
                  >
                    <path
                      fill="currentColor"
                      d="M6 19c0 1.1.9 2 2 2h8c1.1 0 2-.9 2-2V7H6zM8 9h8v10H8zm7.5-5l-1-1h-5l-1 1H5v2h14V4z"
                    />
                  </svg>
                </button>
              </div>
            </div>
          </div>

          <div class="grid grid-cols-12">
            <div class="col-span-10 pr-8">
              <div class="flex gap-4 items-start">
                <input
                  type="checkbox"
                  class="rounded checked:ring-indigo-500"
                />
                <div class="text-sm leading-relaxed">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Doloremque, impedit accusamus! Magni cum maiores tempora alias
                  unde saepe, temporibus eaque doloremque, nobis deserunt
                  commodi blanditiis quod tempore aspernatur. Similique,
                  facilis.
                </div>
              </div>
            </div>

            <div class="col-span-2">
              <div class="flex gap-2 justify-end">
                <button
                  class="border border-blue-200 px-4 py-2 rounded hover:bg-blue-300 transition ease-in-out duration-300"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="16"
                    height="16"
                    viewBox="0 0 24 24"
                  >
                    <path
                      fill="currentColor"
                      d="M5 21q-.825 0-1.412-.587T3 19V5q0-.825.588-1.412T5 3h8.925l-2 2H5v14h14v-6.95l2-2V19q0 .825-.587 1.413T19 21zm4-6v-4.25l9.175-9.175q.3-.3.675-.45t.75-.15q.4 0 .763.15t.662.45L22.425 3q.275.3.425.663T23 4.4q0 .375-.137.738t-.438.662L13.25 15zM21.025 4.4l-1.4-1.4zM11 13h1.4l5.8-5.8l-.7-.7l-.725-.7L11 11.575zm6.5-6.5l-.725-.7zl.7.7z"
                    />
                  </svg>
                </button>

                <button
                  class="border border-rose-200 px-4 py-2 rounded hover:bg-rose-300 transition ease-in-out duration-300"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="16"
                    height="16"
                    viewBox="0 0 24 24"
                  >
                    <path
                      fill="currentColor"
                      d="M6 19c0 1.1.9 2 2 2h8c1.1 0 2-.9 2-2V7H6zM8 9h8v10H8zm7.5-5l-1-1h-5l-1 1H5v2h14V4z"
                    />
                  </svg>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- card actions -->
      <div class="p-4 mt-4 border-solid border-t border-slate-100">
        <div class="grid grid-cols-3 divide-x">
          <div class="col-span-1 text-center px-4">
            <span class="text-slate-600 text-xs">
              Total <span class="font-bold text-indigo-700">(0)</span>
            </span>
          </div>
          <div class="col-span-1 text-center px-4">
            <span class="text-slate-600 text-xs">
              Left To do <span class="font-bold text-rose-700">(0)</span>
            </span>
          </div>
          <div class="col-span-1 text-center px-4">
            <span class="text-slate-600 text-xs">
              Completed <span class="font-bold text-teal-700">(0)</span>
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
