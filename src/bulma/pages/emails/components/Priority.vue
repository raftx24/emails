<template>
    <span class="tag is-bold is-small"
        :class="level">
        {{ label }}
    </span>
</template>

<script>
import { mapState } from 'vuex';

export default {
    name: 'Priority',

    props: {
        priority: {
            type: [Number, String],
            required: true,
        },
    },

    computed: {
        ...mapState(['enums']),
        label() {
            return this.enums.emailPriorities._get(this.priority);
        },
        level() {
            return this.enums.emailPriorityLabels._get(this.priority);
        },
    },
};
</script>

<style lang="scss">
</style>
