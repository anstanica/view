<template>
    <div>
        <form  @submit.prevent="handleSubmit">
            <input type="text" name="name" id="name" placeholder="Name" v-model="name">
            <input type="text" name="email" id="email" placeholder="Email" v-model="email">
            <!-- password -->
            <input type="password" name="password" id="password" placeholder="Password" v-model="password">
                <div v-if="passwordError">{{ passwordError }}</div>
            <!-- <input type="password" v-if="!passwordError" name="password" id="password" placeholder="Confirm Password" v-model="confirmPassword"> -->
            <label>Role:</label>
           <select name="listSelect" id="select"  v-model="Role">
                <option value="Web Developer" >Web Developer</option>
                <option value="Teacher">Teacher</option>
                <option value="Magician">Magician</option>
            </select>
            <input type="text" name="phone" id="phone" placeholder="Phone" v-model="phone">
            <input type="text" name="message" id="message" placeholder="Message" v-model="msg">
            <input type="submit" value="Submit" class="mb-12 ">
            
            <label for="skills">Add Skill</label>
            <input type="text" v-model="tempSkill" @keyup="addSkill">
            <div  v-for="skill in Skills" :key="skill" class="flex justify-between bg-slate-500">
                <ul class="inline-flex justify-between items-center ">
                    <li class="mr-2 w-24 h-12 ml-4 " @click="deleteSkill(skill)"> {{ skill }} <button  class="ml-32 h-12 absolute top-0 w-24">Delete</button></li>
                    
                </ul>
             
        </div>
            <!-- accept terms -->
            <div class="terms">
          <input type="checkbox" name="terms" id="terms" v-model="checked" value="terms" required> <span v-if="checked" >Terms Accepted</span>
        <span v-else>Accept Terms And Conditions</span>
        </div>
        </form>
        
        <div class="shadow list-item bg-slate-500">
            <p class="text-center m-6">  {{ name }} {{ email }} {{ phone }} {{ Role }}</p>
        </div>
  
       
    </div>
          
  
</template>

<!-- what is v-model?
https://vuejs.org/v2/guide/forms.html


-->
<script lang="ts">


export default {
    name: "FormView",
    props: [],
    components: {
        
    },
    data() {
        return {
            name: '',
            email: '',
            phone: '',
            Role: 'Web Developer',
            msg : 'msg',
            checked: false,
            tempSkill: '',
            Skills: [],
            passwordError: '',
            password: '',
            confirmPassword: '',
        }
    },
    methods: {
        addSkill(e) {
            if (e.key === ',') {
                this.tempSkill = this.tempSkill.slice(0, -1)
                if (!this.Skills.includes(this.tempSkill)) {
                    
                    this.Skills.push(this.tempSkill)
                }
                // remove the last character
               
                this.tempSkill = ''
            }
        },
        deleteSkill(skill) {
            this.Skills = this.Skills.filter(s => s !== skill)
        },
        handleSubmit() {
           
        //    validate password
        this.passwordError = this.password.length > 5 ?
         '' : 'Password must be at least 6 characters' 
       
    
         
    }
}
}
</script>

<style scoped>

</style>