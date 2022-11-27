<template>
	<div :class="`bg-light task ${task.done ? 'is-complete' : ''}`">
		<div class="content">{{ task.content }}</div>
		<div class="buttons">
			<button @click="toggleDone" class="btn btn-success">{{ task.done ? 'Undo' : 'Done' }}</button>
			<button @click="removeTask" class="btn btn-danger">Delete</button>
		</div>
	</div>
</template>

<script>
export default {
	props: ['task'],
	methods: {
		toggleDone() {
			this.$store.commit('TOGGLE_TASK', this.task);
		},
		removeTask() {
			this.$store.commit('REMOVE_TASK', this.task);
		}
	}
}
</script>

<style>

</style>
