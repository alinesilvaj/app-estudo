<script>
import SearchTask from './components/SearchTask.vue'
import SearchTaskCategory from './components/SearchTaskCategory.vue'
import TitleApp from './components/TitleApp.vue'
import TitleCategories from './components/TitleCategories.vue'
import CategoriesApp from './components/CategoriesApp.vue'
import TitleTasks from './components/TitleTasks.vue'
import TasksApp from './components/TasksApp.vue'
import ButtonDelete from './components/ButtonDelete.vue'
import ButtonPlus from './components/ButtonPlus.vue'
import ButtonClose from './components/ButtonClose.vue'
import InputTask from './components/InputTask.vue'
import CategoryType from './components/CategoryType.vue'
import ButtonNewTask from './components/ButtonNewTask.vue'

//let itemElement = document.querySelectorAll('li')

export default {
  components: {
    SearchTask,
    SearchTaskCategory,
    TitleApp,
    TitleCategories,
    CategoriesApp,
    TitleTasks,
    TasksApp,
    ButtonDelete,
    ButtonPlus,
    ButtonClose,
    InputTask,
    CategoryType,
    ButtonNewTask
  },
  data: () => ({
    cards: [
      {
        title: 0,
        subTitle: 'Business',
        progress: 0,
        barraBusiness: true,
        barraPersonal: false
      },
      {
        title: 0,
        subTitle: 'Personal',
        progress: 0,
        barraBusiness: false,
        barraPersonal: true
      }
    ],
    tasks: [
      {
        name: 'checar e-mail do trabalho',
        isDone: false,
        checkBusiness: true,
        checkPersonal: false
      }
    ],
    selected: null,
    options: [
      { value: null, text: 'Select one category' },
      { value: true, text: 'Business' },
      { value: false, text: 'Personal' }
    ],
    currentTask: '',
    checkCategory: '',
    searchTask: '',
    pageTasksList: false,
    pageAddTask: true
  }),
  computed: {
    computedCards() {
      if (this.tasks.length == 0) {
        return this.cards.map((card) => ({
          ...card,
          title: this.getTasksByCard(card).length,
          progress: 0
        }))
      }
      return this.cards.map((card) => ({
        ...card,
        title: this.getTasksByCard(card).length,
        progress: this.getTasksByCard(card).length * 100 / this.tasks.length
      }))
    },
    tasksFiltered() {
      let valores = []

      valores = this.tasks.filter((task) => {
        return task.name.toLowerCase().indexOf(this.searchTask.toLowerCase()) > -1
      })

      valores = valores.filter((task) => {
        if (this.selected === null) {
          return task
        }
        return task.checkBusiness === this.selected
      })

      return valores
    }
  },
  methods: {
    showSearchBar() {
      this.searchBar = !this.searchBar
    },
    getTasksByCard(card) {
      return this.tasks.filter((task) => this.checkTaskIsBusinessByCard(card, task))
    },
    checkTaskIsBusinessByCard(card, task) {
      if (card.barraBusiness) {
        return task.checkBusiness
      }
      return task.checkPersonal
    },
    createTask(name, checkBusiness) {
      return { name, isDone: false, checkBusiness, checkPersonal: !checkBusiness }
    },
    validTasks() {
      let isValid = true

      if (!this.currentTask || !this.checkCategory) {
        alert('Enter new task and choose a category for your task: BUSINESS OR PERSONAL')
        isValid = false
        this.changePage()
      }

      return isValid
    },
    addTask() {
      if (this.validTasks()) {
        const isBusiness = this.checkCategory == 'Business'
        this.tasks.push(this.createTask(this.currentTask, isBusiness))
      }
      this.changePage()
    },
    remove(task) {
      this.tasks = this.tasks.filter((t) => t.name !== task.name)
    },
    changePage() {
      this.pageAddTask = !this.pageAddTask
      this.pageTasksList = !this.pageTasksList
    }
  }
}
</script>

<template>
  <div :class="{ pageTasksList: pageTasksList }">
    <nav>
      <div class="pesquisa">
        <SearchTask v-model="searchTask" />

        <div>
          <select name="" class="select">
            <SearchTaskCategory
              v-for="(option, index) in options"
              :key="index"
              v-model="selected"
              :options="option"
            />
          </select>
        </div>
      </div>
    </nav>

    <TitleApp text="What's up!" />

    <div class="categorias">
      <TitleCategories />
      <div class="tipos-categorias">
        <CategoriesApp
          v-for="(card, index) in computedCards"
          :key="index"
          :title="card.title"
          :subTitle="card.subTitle"
          :progress="card.progress"
          :barraBusiness="card.barraBusiness"
          :barraPersonal="card.barraPersonal"
        />
      </div>
    </div>

    <div class="tarefas">
      <TitleTasks />

      <ul class="lista-tarefas">
        <li v-for="(task, index) in tasksFiltered" :key="index">
          <div class="itemTarefa">
            <TasksApp
              @click="task.isDone = !task.isDone"
              :tarefa="task"
              :checkBusiness="task.checkBusiness"
              :checkPersonal="task.checkPersonal"
            />
            <ButtonDelete @click="remove(task)" />
          </div>
        </li>
      </ul>
    </div>

    <ButtonPlus @click="changePage" />
  </div>

  <div :class="{ pageAddTask: pageAddTask }">
    <ButtonClose @click="changePage" />

    <InputTask v-model="currentTask" @keyup.enter="addTask" />

    <CategoryType v-model="checkCategory" />

    <ButtonNewTask @click="addTask" />
  </div>
</template>

<style scoped>
.pageTasksList {
  display: none;
}

.pageAddTask {
  display: none;
}
</style>
