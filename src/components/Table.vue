<template>
    <div class="data-table-container">
        <table class="table-fixed" cellspacing="0">
            <thead class="data-list-head">
                <tr>
                    <th
                        v-for="(val, index) in tableOrder"
                        :key="index"
                    >{{ val }}</th>
                </tr>
            </thead>
            <tbody>
                <tr
                    v-for="(row, index) in computedData"
                    :key="index"
                >
                    <td
                        v-for="(key, idx) in tableOrder"
                        :key="idx"
                    >
                        <span v-if="key !== 'picture'">{{ row[key] }}</span>
                        <img class="data-list-image" :src="row[key]" v-if="key === 'picture'" />
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: 'Table',
    props: ['data', 'searchTerm'],
    data: () => ({
        tableOrder: ['name', 'picture', 'email']
    }),
    computed: {
        computedData () {
            return this.data.filter(
                row =>
                    row.name.includes(this.searchTerm) ||
                    row.email.includes(this.searchTerm))
        }
    }
}
</script>

<style lang="scss">
.data-list-image {
    width: 80px;
    height: 80px;
}

.table-fixed {
    width: 101%;
    border-top: none;
    border-bottom: none;
    background-color: #fff;
    td {
        text-align: left;
        border-bottom: 1px solid rgba(0,0,0,0.1);
        padding-top: 10px;
        padding-bottom: 5px;
        padding-left: 10px;
        padding-right: 10px;
    }
    tbody tr:nth-child(odd) {
        background: rgba(0,0,0,0.02);
    }
}

/*This will work on every browser but Chrome Browser*/
.table-fixed thead {
    font-size: 12px;
    position: sticky;
    position: -webkit-sticky;
    top: 0;
    z-index: 999;
    background-color: #000;
    color: #fff;
}

/*This will work on every browser*/
.table-fixed thead th {
    text-align: left;
    position: sticky;
    position: -webkit-sticky;
    top: 0;
    z-index: 999;
    background-color: #EAEAEA;
    color: black;
    padding-left: 10px;
    padding-right: 10px;
    &:last-child {
        border-top-right-radius: 5px;
    }
    &:first-child {
        border-top-left-radius: 5px;
    }
    border-right: 1px solid #EAEAEA;
}

.data-table-container {
    height: 70vh;
    overflow: scroll;
    border: 1px solid rgba(0,0,0,0.1);
    border-radius: 5px;
}
</style>
