<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <ar-flex-box justify="center">
            <ar-segmented
                :key="segmented.length"
                size="default"
                v-model="input"
                :options.prop="segmented"
                :block="true"
            ></ar-segmented>
            <el-button @click="add" type="primary">Add</el-button>
            <el-input v-model="input" style="width: 200px"></el-input>
        </ar-flex-box>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'HelloWorld',
    props: {
        msg: String,
    },
    data: function () {
        return {
            segmented: ['A', 'B'],
            input: 'A',
        };
    },
    methods: {
        add() {
            this.segmented.push('C');
        },
    },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
