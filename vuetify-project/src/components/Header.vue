<template>
  
    <!--<v-card>
      <v-app-bar flat color="primary">
        <v-container class="fill-height d-flex align-center">
          
          
          
          <v-app-bar-title
              class="flex text-center"
              color="blue"
              variant="text"
            >
            <v-app-bar-nav-icon
              
              size="32"
            ></v-app-bar-nav-icon>
              {{ title }}
          </v-app-bar-title>
          
        </v-container>
        
        <AddButton text="Add"/>
      </v-app-bar>
    </v-card>-->
    

      <v-app-bar color="primary">
        <!-- Creating Frameowrks title-->
        <v-toolbar-title
        class="flex text-center" dense>
            <v-app-bar-nav-icon 
              size="32"
            ></v-app-bar-nav-icon>
          {{title}}
          {{ subtitle }}
        </v-toolbar-title>
        <!--Adding Button-->
        <AddButton @task-added="$emit('task-added', task)" addBtn/>
        
        
        
        
        
      </v-app-bar>
      
      
     
    
    <!-- creating the sub header-->
  

</template>

<script>
import AddButton from '@/components/AddButton.vue'
import Table from '@/components/Table.vue'

  export default {
  props: {
    title: String,
    subtitle: String
  },
  components: {
    AddButton,
  },
  data() {
    return {
      
    }
  },
  emits: ['task-added']
  
}
</script>