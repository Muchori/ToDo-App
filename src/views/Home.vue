<!-- eslint-disable vue/multi-word-component-names -->
<template>
	<div class="bg-indigo-500">
		<div>
			<ToDoInput @eventAddNewTask="onAddNewTask"/>

			<!-- <ul class="list mt-3">
				<ListItem v-for="item in itemList" :key="item.id" :text="item.text" :id="item.id" :isDone="item.isDone" @eventTaskStatusChange="onTaskStatusChange" @eventTaskDelete="onTaskDelete" />
			</ul> -->
		</div>
	</div>
</template>

<script>
	import ToDoInput from "../components/ToDoInput.vue"
	//import ListItem from "@/components/ListItem.vue"

	export default {
		// eslint-disable-next-line vue/multi-word-component-names
		name: "Home",
		components: {
			ToDoInput,
		},
		data() {
            return {
                itemList: []
            }
        },
    methods: {
      /**
       * Event: add new task
       */
      onAddNewTask(taskName) {
        const task = {
          id: (new Date()).getTime(),
          text: taskName,
          isDone: false
        }

        this.itemList.push(task)
      },
    }
	}
</script>
