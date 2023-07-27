<template>
  <q-page class="bg-grey-3 column">
    <div class="row q-pa-sm bg-primary">
      <q-input 
        class="col"
        square="filled"
        v-model="newTask" 
        placeholder="Add Task" 
        bg-color="white"
        @keyup.enter="addTask"
        dense
      >
        <template v-slot:append>
          <q-btn 
            round 
            dense 
            flat 
            icon="add" 
            @click="addTask"
          />
        </template>
      </q-input>
    </div>
    <q-list class="bg-white"
      separator
      bordered
    >
      <!--
        Rendering a <label> tag (notice tag="label")
        so QCheckboxes will respond to clicks on QItems to
        change Toggle state.
      -->

      <q-item 
        v-for="(task, index) in tasks" 
        :key="task.title"
        @click="task.done = !task.done"
        :class="{ 'done bg-blue-1' : task.done}"
        clickable
        >
        <q-item-section avatar>
          <q-checkbox 
          v-model="task.done" 
          color="primary" 
          class="no-pointer-events"
          />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{ task.title }}</q-item-label>
        </q-item-section>
        <q-item-section v-if="task.done" side>
          <q-btn 
            @click.stop="deleteTask(index)"
            flat 
            round 
            dense
            color="primary" 
            icon="delete" 
          />
        </q-item-section>
      </q-item>

    </q-list>
    <div 
      v-if="!tasks.length"
      class="no-tasks absolute-center"
      >        
      <q-icon 
          name="check"
          size="100px"
          color="primary"
        />
      <div class="text-h5 text-primary text-center">
        No Task
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import { useQuasar } from 'quasar'

export default defineComponent({
  name: 'IndexPage',
  data() {
    const $q = useQuasar()
    function deleteConfirm (index) {
      $q.dialog({
        title: 'deleteConfirm',
        message: 'Really Delete This? :(',
        cancel: true,
        persistent: true
      }).onOk(() => {
        // console.log('>>>> second OK catcher')
        this.tasks.splice(index,1)
        // notify
        $q.notify('Task deleted!')
      })
    };
    return {
      newTask: '',
      tasks: [
        // {
        //   title: 'Get Bananas',
        //   done: false
        // },
        // {
        //   title: 'Eat Bananas',
        //   done: true
        // },
        // {
        //   title: 'Pop Bananas',
        //   done: false
        // },
      ],
      deleteConfirm
    }
  },
  methods: {
    deleteTask(index) {
      this.deleteConfirm(index)
    },
    addTask() {
      // console.log('add task')
      this.tasks.push({
        title: this.newTask,
        done:false
      })
      // reset
      this.newTask = ''
    }
  }
});
</script>

<style>
.done .q-item__label {
  text-decoration: line-through;
  color: #bbb;
}
.no-tasks {
  opacity: 0.5;
}
</style>

