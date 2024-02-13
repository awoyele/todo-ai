<template>
    <form>
        <input type="text" v-model="task.title" placeholder="Enter task">
        <input type="text" v-model="task.description" placeholder="Enter description">
        <button @click="addTask">Add Task</button>
    </form>
</template>

<script setup>
import { reactive, ref } from 'vue';

let tasks = reactive([]);
let task = reactive({ title: '', description: '', status: 'active' });

const addTask = () => {
    tasks.push({ ...task });
    task.title = '';
    task.description = '';
};

const modifyTask = (index, newTitle, newDescription, newStatus) => {
    tasks[index].title = newTitle;
    tasks[index].description = newDescription;
    tasks[index].status = newStatus;
};

<script>

<style>
</style>