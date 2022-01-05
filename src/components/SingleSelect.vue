<!-- -->


<template>
    <div class="singleSelect">
        <label for="basicComboBox"> Framework
        <ComboBoxAbstract
            id="basicComboBox"
            :labelProp="labelText"
            :placeholderProp="placeholderText"
            :optionsProp="staticData"
            v-model="selectedData"
            :multipleProp="true"
            :taggableProp="true"
            :pushTagsProp="true"
            :required="selectedData"
        >
        </ComboBoxAbstract>
        </label>
        <span>{{selectedData}}</span>

    </div>
</template>

<script>
import ComboBoxAbstract from './ComboBoxAbstract.vue'
    export default {
        name: 'SingleSelect',
        components: {ComboBoxAbstract},
        data(){
            return {
                labelText: "frameworkName",
                feedbackText: "Create or select tag...",
                placeholderText: "Choose a Option...",
                selectedData: [],
                staticData: [
                    {frameworkName: 'Vue', code: 'ca'},
                    {frameworkName: 'React', code: 'US'},
                    {frameworkName: 'Angular', code: 'US'},
                    {frameworkName: 'Javascript', code: 'US'},
                    {frameworkName: 'Svelte', code: 'US'}
                ]
            }
        },
        
    }
</script>

<style scoped>
.singleSelect {
    width: 30%;
    margin: 10px;
}
label {
    padding: 10px;
}
</style>