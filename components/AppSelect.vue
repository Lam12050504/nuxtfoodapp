<template>
    <div>
        <label  :for="select">Which is your favorite {{select}}?</label>
        <select name="select" id="select" @change="$emit('change',$event.target.value)">
            <option value="">--Plese select the {{select}}--</option>
            <option v-for="option in selectOption" :key="option" :value="option">{{option}}</option>
        </select>
    </div>
</template>

<script>
export default {
    props: {
        select: {
            type: String,
            default: "cuisine"
        },
        selectOption: {
            type: Array,
            default: () => ['tacos','pizza','dim sum',]
        }
    }
}
</script>

<style lang="scss" scoped>

</style>