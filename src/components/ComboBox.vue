<template>
    <div id="comboBox">
        <h3>Vue Select</h3>

        <h5>Single Option Selected with Basic Operations [Array]</h5>
        <v-select :options="options"></v-select>

        <h5>Single Option Selected with Basic Operations [Array Object]</h5>
        <v-select :options="arrayObjects"></v-select>

        <h5>Single Option Selected with Basic Operations [Label,Array Object]</h5>
        <v-select label="countryName" :options="labelObjects"></v-select>

        <h5>Single Option Selected with Basic Operations [Label,Array Object,Get Selected Value]</h5>
        <v-select multiple v-model="selected" label="countryName" :options="labelObjects"></v-select>
        {{selected}}

        <h5>Single Option Selected with Basic Operations [Label,Array Object,Get Particular Value]</h5>
        <v-select multiple v-model="selected" :reduce="a => a.code" label="countryName" :options="labelObjects"></v-select>
        {{selected}}

        <h5>Tag</h5>
        <v-select taggable multiple />

        <h5>Tag with push</h5>
        <v-select taggable multiple push-tags :options="arrayObjects" :create-option="book => ({ label: '',code:''} )" :reduce="a => a.label"/>

    </div>
</template>
<script>
export default {
    name: 'ComboBox',
    data() {
        return {
            options: ['Vue 1','Vue 2','Vue 3'],
            array: [],
            arrayObjects: [{label: 'Canada', code: 'ca'},{label: 'America', code: 'US'}],
            labelObjects: [{countryName: 'Canada', code: 'ca'},{countryName: 'America', code: 'US'}],
            selected: []
        }
    },
}
</script>
<style lang="">
    
</style>