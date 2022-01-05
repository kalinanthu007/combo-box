<template>
    <div>
        <label for="basicComboBox">
            Select Framework
            <v-select 
                class="style-chooser"
                id="basicComboBox"
                :label="labelText"
                :placeholder="placeholderText" 
                v-model="selectedFramework" 
                :options="staticData"
            />
                 <span slot="no-options" >{{feedbackText}}</span>
        </label>
        <div>
        {{selectedFramework}}
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ComboBox1',
        data(){
            return {
                labelText: "frameworkName",
                feedbackText: "Create or select tag",
                placeholderText: "Choose a Framework Option",
                selectedFramework: [],
                staticData: [
                    {frameworkName: 'Vue', code: 'ca'},
                    {frameworkName: 'React', code: 'US'},
                    {frameworkName: 'Angular', code: 'US'},
                    {frameworkName: 'Javascript', code: 'US'},
                    {frameworkName: 'Svelte', code: 'US'}
                ]
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

/*.style-chooser .vs__dropdown-toggle,
.style-chooser .vs__dropdown-menu {
  background: #dfe5fb;
  border: none;
  color: #394066;
  text-transform: lowercase;
  font-variant: small-caps;
}

.style-chooser .vs__clear,
.style-chooser .vs__open-indicator {
  fill: #394066;
}*/
</style>