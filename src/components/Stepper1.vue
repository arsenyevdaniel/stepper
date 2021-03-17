
<template>
    <div>
 <v-stepper v-model="numStep">
     <v-stepper-header>
                <v-stepper-step :complete="numStep > 1" step="1">
                    Step1
                </v-stepper-step>
                 <v-divider></v-divider>
                <v-stepper-step :complete="numStep > 2" step="2">
                    Step2
                </v-stepper-step>
                 <v-divider></v-divider>
                <v-stepper-step :complete="numStep > 3" step="3">
                    Step3
                </v-stepper-step>
    </v-stepper-header>
      <v-stepper-items>

        <v-stepper-content step="1">   
     <form>
         <div class="container">
        <h1>Dog's passport</h1>
        <p></p>
        <hr>
          <label for="name"><b>DOG'S NAME</b></label>
          <input v-model ="name" type="text" placeholder="Enter Name" name="name" required>
          <label for="surname"><b>DOG'S SURNAME</b></label>
          <input v-model="surname" type="text" placeholder="Enter Surname" name="surname" required>

          <p>{{Error}}</p>
          <div class="button" @click="click_button1">Next</div>
         </div>
    </form>
        </v-stepper-content>

            <v-stepper-content step="2">
     <form>
        <div class="container">
        <h1>Information</h1>
        <hr>

    <label for="breed"><b>Breed</b></label>
    <input v-model="Breed" type="Information" placeholder="Enter Breed" name="breed" required>
    <label for="gender"><b>Gender</b></label>
    <input v-model="gender" type="Information" placeholder="Enter Gender" name="gender" required>
    <label for="data"><b>Year of birth</b></label>
    <input v-model="data" type="Information" placeholder="Enter " name="data" required>
    <hr>
    <p>{{Error}}</p>
    <div class="button" @click="click_button2">Next</div>

  </div>
</form>        
 </v-stepper-content>
            <v-stepper-content step="3">
               <form>
        <div class="container">
        <h1>Паспорт создан!</h1>
        
        <hr>
                         <p>Имя собаки: {{name}} </p>
                         <p>Фамилия собаки: {{surname}}</p>
                         <p>Порода: {{Breed}}</p> 
                         <p>Пол: {{gender}}</p> 
                         <p>Дата рождения: {{data}}</p> 
                        <div class="button" @click="click_reset">Resert</div>
  </div>
</form>
            </v-stepper-content>
        </v-stepper-items>
        </v-stepper>
  </div>
   
</template>


<script >

export default {
    name: 'Stepper1',

    data: function(){
    return { 
      
        name:"",
        surname:"",
        dd:"2",
        Breed:"",
        gender:"",
        data:"",
        Error:"",
        numStep: 1
    }
      
    },
    methods:{
click_button1: function() {

    if(this.name=="" || this.surname=="")
      this.Error = "Enter your data"

    else
     {
        this.numStep = this.numStep+1
        this.Error=""
     }

  
},
click_button2: function() {

   
    if (this.dd == 2){
      if((this.gender!="Мужской" && this.gender!="Женский" && this.gender!="Ж" && this.gender!="М")){
      this.Error = "Wrong gender entered"   
       this.dd = 1;
      }
      else
      {
        this.numStep = this.numStep+1
        this.Error=""
        this.dd = 1;
      }
    }

    if (this.dd == 2){
      if((this.gender==""||this.data=="")||(this.breed =="")){
        this.Error = "Enter your data"   
      }
     else
      {
      this.numStep = this.numStep+1
      this.Error=""
      this.dd = 2;
      }
    }
    this.dd = 2;
    
    
},
click_reset : function() {
    this.numStep=1
    this.name=""
    this.surname=""
    this.Breed=""
    this.password2=""
    this.gender=""
    this.data=""
}, 


}
}
</script>
<style scoped>
* {box-sizing: border-box}

/* Add padding to containers */
.container {
  padding: 100px;
  background-image:url(https://img2.goodfon.ru/original/2200x1305/f/d9/art-emma-jonsson-sobaka.jpg);
  width: 1800px;
  height: 700px;
}

/* Full-width input fields */
input[type=text], input[type=Information] {
  width: 100%;
  padding: 25px;
  margin: 12px 0px 12px 30px;
  display: inline-block;
  border: none;
  background: #FA8072;
}

input[type=text]:focus, input[type=Information]:focus {
  background-color: #ddd;
  outline: none;
}

/* Overwrite default styles of hr */
hr {
  
  border: 1px dotted #362a2a;
  margin-bottom: 25px;
}

/* Set a style for the submit/register button */
.button {
  background-color: brown; /* Green */
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
}

.registerbtn:hover {
  opacity:1;
}

/* Add a blue text color to links */
a {
  color: red;
}

/* Set a grey background color and center the text of the "sign in" section */
.signin {
  background-color: red;
  text-align: center;
}
</style>