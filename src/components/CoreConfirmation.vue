<template>
    <dropdown v-bind="$attrs"
        v-on="$listeners"
        ref="dialog">
        <slot/>
        <template #:popper>
            <slot name="confirm"
                :confirm="confirm"/>
            <slot name="cancel"
                :cancel="cancel"/>
        </template>
    </dropdown>
</template>

<script>
import { Dropdown } from 'v-tooltip';

export default {
    name: 'CoreConfirmation',

    components: { Dropdown },

    methods: {
        hide() {
            this.$refs.dialog.hide();
        },
        cancel() {
            this.hide();
            this.$emit('cancel');
        },
        confirm() {
            this.hide();
            this.$emit('confirm');
        },
    },
};
</script>
