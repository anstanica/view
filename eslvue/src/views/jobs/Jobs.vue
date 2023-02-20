<template>
    <div>
        <h1>Jobs</h1>
        <div class="flex flex-col container">
            <!-- jobs list-->

            <div v-for="job in jobs" :key="job['id']" class="flex flex-col bg-white shadow-md rounded-lg p-6 mb-4">
                <div class="flex justify-between">
                    <h3 class="text-xl font-medium text-gray-800">{{ job['title'] }}</h3>
                    <span class="text-gray-500">{{ job['created_at'] }}</span> 

                    <RouterLink :to="{ name: 'JobDetails', params: { id: job['id'] }}" class="text-blue-500">View</RouterLink>
                   </div>
            </div>
    </div>
    </div>
</template>

<script lang="ts">

export default {
    name: "Jobs",
    components: {
        
    },
    data() {
        return {
            // add jobs properties type


            jobs: [


            ],

        }
    },
    mounted() {
        this.getJobs();
    },
    methods: {
        getJobs() {
            fetch('http://localhost:3000/jobs')
            .then(response => response.json())
            .then(data => {
                this.jobs = data;
            }).catch(error => {
                console.log(error);
            });
        }
    }
}

</script>

<style  scoped>

</style>