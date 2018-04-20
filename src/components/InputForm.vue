<template>
    <div>
        <form>
            <label>Apply Here: </label>
            <textarea id='application-text' cols='100' rows='8' v-model='formText'></textarea>
            <input id= 'submit' type='submit' value='Submit' @click.prevent.reset = 'submitForm'/>
        </form>
        <p id='message'>{{message}}</p>
    </div>
</template>

<script>
export default {
    name: 'InputForm',
    props: {
        getText: {
            type: Function,
            required: true
        }
    },
    data () {
        return {
            formText: '',
            message: '',
        }
    },
    watch: {
        formText (newText) {
            this.getText(newText)
        }
    },
    methods: {
        submitForm(){
            this.message = 'Your application was submitted!',
            this.formText = ''
        }
    }
}
</script>

<style scoped>
form {
  display: block;
}
</style>

