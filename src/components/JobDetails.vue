<template>
    <div>
        <h2>Job Details</h2>
        <h3>{{listings.title}}</h3>
    </div>
</template>

<script>
export default {
    name:'JobDetails',
    props: {
        listings: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>

</style>

