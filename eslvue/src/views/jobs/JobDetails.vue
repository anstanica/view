<template>
    <div>
        <h1 class="text-3xl font-bold leading-tight">Job Details</h1>
       
        <div class="flex justify-between m-6 p-6 ">
            <h1 class="m-2 font-bold text-2xl" >{{ job['title'] }}</h1> 

            
            <h3 class="text-xl font-bold m-2">The Job id is : {{ id }}</h3>
        

           </div>
           <div class="text-3xl">
            <h3>
                {{ job['description'] }}
            </h3>
           </div>

    </div>
</template>

<script lang="ts">

export default {
    props: ['id',
],
   
    data() {
        return {
            job: [],
        }
    },
    mounted() {
        this.getJob();
    },
    methods: {
        getJob() {
            fetch('http://localhost:3000/jobs/' + this.id)
            .then(response => response.json())
            .then(data => {
                this.job = data;
            }).catch(error => {
                console.log(error);
            });
        }
    }
};
</script>

<style scoped>

</style>