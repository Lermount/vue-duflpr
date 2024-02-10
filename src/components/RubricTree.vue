<template>
<div class="mt-4">
    <label class="mb-2 form-check-label">
        <input class="form-check-input" type="checkbox" v-model="showEmptyRubrics"> Отображать пустые рубрики
    </label>

    <div class="mb-2">
        <span v-if="selectedRubrics.length >= 0">Сумма count-ов отмеченных рубрик: {{ total }}</span>
    </div>
    
    <tree-node v-for="rubric in rootRubric" :key="rubric.id" :rubric="rubric" :show-empty-rubrics="showEmptyRubrics"
        @rubricSelected="handleRubricSelected" :selected-rubrics="selectedRubrics"></tree-node>
</div>
</template>

<script>
import axios from 'axios';
import TreeNode from './TreeNode.vue';

export default {
components: {
    TreeNode,
},
data() {
    return {
        rootRubric: null,
        showEmptyRubrics: false,
        selectedRubrics: [],
        total: 0,
    };
},

watch: {
    showEmptyRubrics() {
        this.getRubrics()
    },

    selectedRubrics() {
        this.updateTotal()
    }
},

mounted() {
    this.getRubrics();
},

methods: {
    getRubrics() {
        const allowEmpty = this.showEmptyRubrics ? 1 : 0;
        axios.get(`https://www.klerk.ru/yindex.php/v3/event/rubrics?allowEmpty=${allowEmpty}`)
            .then(response => {
                this.rootRubric = response?.data || {};
            })
            .catch(error => {
                console.error(error);
            });
    },

    handleRubricSelected(selectedRubric) {
        const index = this.selectedRubrics.findIndex(rubric => rubric.id === selectedRubric.id);

        if (index !== -1) {
            this.selectedRubrics.splice(index, 1);
        } else {
            this.selectedRubrics.push(selectedRubric);
        }
    },

    updateTotal() {
        this.total = this.selectedRubrics.reduce((acc, rubric) => acc + rubric.count, 0);
    },
},
};
</script>