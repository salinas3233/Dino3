<template>
    <div>
        <section>
            <p id='application-preview'>{{text}}</p>
        </section>
    </div>
</template>

<script>
export default {
    name: 'Preview',
    props: {
        text: {
        type: String,
        required: false
        }
    }
}
</script>

<style scoped>
#application-preview {
  border-radius: 6px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
  border: 1px solid darkgrey;
  min-height: 100px;
  margin-top: 20px;
  padding: 10px;
}
</style>
