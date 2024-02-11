<template>
    <div>
        <div class="mb-1">
            <div class="rubric">
                <input class="me-1 form-check-input" type="checkbox" v-model="isSelected" @click="handleRubricClick">
                <a class="form-check-label" :href="rubric.url">{{ rubric.title }}</a> ({{ rubric.count }}, {{ totalCount == 0 ? 0 : totalCount + rubric.count }})
            </div>
        </div>
        <div class="mb-1 ps-3" v-show="rubric && rubric.children && isSelected">
            <tree-node v-for="child in rubric.children" :key="child.id" :rubric="child"
                :show-empty-rubrics="showEmptyRubrics" :selected-rubrics="selectedRubrics"
                @rubricSelected="handleChildRubricSelected">
            </tree-node>
        </div>
    </div>
</template>

<script>
export default {
    name: 'treeNode',

    props: {
        rubric: {
            type: Object,
            required: true,
        },

        showEmptyRubrics: {
            type: Boolean,
            required: true,
        },

        selectedRubrics: {
            type: Array,
            required: true,
        }
    },

    data() {
        return {
            isSelected: false,
        };
    },

    methods: {
        handleRubricClick() {
            this.isSelected = !this.isSelected;
            this.$emit('rubricSelected', this.rubric, this.isSelected);
        },

        handleChildRubricSelected(childRubric, isSelected) {
            this.$emit('rubricSelected', childRubric, isSelected);
        },
    },

    computed: {
        totalCount() {
            const commonCount = this.rubric?.children?.map(item => item.count) 
            const total = commonCount?.reduce((acc, rubric) => acc + rubric, 0)
            if(commonCount) {
                return total
            } else {
                return 0
            }
        },

        checkedRubrics() {
            return this.selectedRubrics.filter(item => item.id == this.rubric.id)
        }
    }
};
</script>