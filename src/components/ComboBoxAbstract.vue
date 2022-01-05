<!-- Define props -->
<template>
    <v-select 
        class="style-chooser"
        :label="labelProp"
        :placeholder="placeholderProp" 
        v-model="model"
        :options="optionsProp"
        :multiple="multipleProp"
        :taggable="taggableProp"
        :pushTags="pushTagsProp"
        >
            <span slot="no-options" >{{feedbackProp}}</span>
    </v-select>
</template>

<script>
    export default {
        name:'ComboBoxAbstract',
        props:{
            selectedValue:{type:Array,default:null},
            labelProp: {type: String,default: "label"},
            placeholderProp: {type: String,default: "Choose Option"},
            optionsProp: {type: Array,default() {return [];}},
            searchable: {type: Boolean,default: true},
            loading: {type: Boolean,default: true}, //Show spinner if the component is in a loading state.
            multipleProp: {type: Boolean,default: false},
            pushTagsProp: {type: Boolean,default: false},
            taggableProp: {type: Boolean,default: false},
            feedbackProp:{type: String,default: "Create or Select Tag"},
        },
        data(){
            return {
                model: this.selectedValue
            }
        },  
        watch: {
            model(currentValue){
                this.$emit('input',currentValue)
            }
        }
    }
</script>

<style>
.style-chooser .vs__search::placeholder{
    color:grey;
    font-size:12px;
    font-weight: normal;  
}
</style>