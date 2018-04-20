<template>
    <div>
        <h2>Job Details</h2>
        <h4>{{jobData.title}}</h4>
        <p>{{jobData.description}}</p>
    </div>
</template>

<script>
export default {
    name:'JobDetails',
    props: ['jobData']
}
</script>

<style scoped>

</style>

