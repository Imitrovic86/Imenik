<script>
export default {
    name: "Footer",
    data() {
        return {
            contentName: "",
            contentNumber: "",
        };
    },
    methods: {
        onAddClick() {
            this.$emit("add", [this.contentName, this.contentNumber]);
        },
        onDeleteClick() {
            this.$emit("delete", [this.contentName, this.contentNumber]);
        }
    },
};
</script>


<template>
    <footer>
        <input v-model="contentName" id="content" type="text" placeholder="addName" >
        <input v-model="contentNumber" id="content" type="text" placeholder="addNumber" >
        <span id="add-btn" v-on:click="onAddClick">Add</span>
        <span id="add-btn" v-on:click="onDeleteClick">Delete</span>
    </footer>

</template>

<style scoped>
footer {
    display: flex;
    padding: 8px 4px;
    align-items: center;
    flex-shrink: 0;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;

    background-color: #f5f5f5;
}

input {
    border: none;
    padding: 8px;

    flex-grow: 1;

    background: transparent;
}

input:focus,
input:active,
input:hover {
    border: none;
    outline: none;
}

#add-btn {
    padding-right: 14px;
    font-weight: bold;
    cursor: pointer;
    color: grey;
}

#add-btn:hover {
    color: rgb(58, 58, 58);
}
</style>
