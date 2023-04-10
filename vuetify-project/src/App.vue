<template>
  <v-app >
    <v-card class="mt-9">
      <v-card-title>
        <v-app-bar color="primary">
        <!-- Creating Frameowrks title-->
        <v-toolbar-title
        class="flex text-center" dense>
            <v-app-bar-nav-icon 
              size="32"
            ></v-app-bar-nav-icon>
          FRAMEWORKS
          {{ subtitle }}
        </v-toolbar-title>
        <!--Adding Button-->
        <AddButton @task-added="addTask" :taskList="this.tasks" addBtn/>
        
        
        
        
        
      </v-app-bar>
      </v-card-title>
      
      <v-container fluid>
        <Table :tasks="tasks"/>
      </v-container>
    </v-card>
  </v-app>
  
</template>

<script>
  import Header from '@/components/Header.vue'
  import Table from '@/components/Table.vue'
  import AddButton from './components/AddButton.vue'

  export default{
    components: {
      Header,
      Table,
      AddButton
    },
    methods: {
      addTask(newTask){
        console.log("wow")
        
        //const newTask = {
          //      title: this.$refs.addButton.title,
            //    description: this.$refs.addButton.description,
              //  deadline: this.$refs.addButton.deadline,
                //priority: this.$refs.addButton.priority
            //}
            
              console.log(newTask)
              this.tasks.push(newTask)
            
            
            
           // this.$refs.addButton.dialogVisible = false
           

            
        
        
      },
      deleteTask(){
        console.log("todo deleted")
        this.tasks = this.tasks.filter((task) => task.title !== title)
      }
    },
    data(){
      return{
        tasks: [],
        isTitleUnique: null,
      }
    }
  }
</script>
