<template>
    <div class="input-container">
        <div class="search-icon">&#x1F50D;</div>
        <input
            type="text"
            v-model="searchTerm"
            @input="$emit('input', $event.target.value)"
        />
    </div>
</template>

<script>
export default {
    data: () => ({
        searchTerm: '',
    })
}
</script>

<style scoped>
input:focus {
    outline: none;
}

input {
    border: 0;
    width: 100%;
    font-size: 14px;
    margin-left: 5px;

}

.input-container {
    border: 1px solid rgba(0,0,0,0.1);
    width: 300px;
    border-radius: 5px;
    display: flex;
    margin-bottom: 5px;
}

.search-icon {
    margin-left: 5px;
}
</style>
