<template>
    <v-popover v-bind="$attrs"
        v-on="$listeners"
        ref="dialog">
        <slot/>
        <template v-slot:popover>
            <slot name="confirm"
                :confirm="confirm"/>
            <slot name="cancel"
                :cancel="cancel"/>
        </template>
    </v-popover>
</template>

<script>

import { VPopover } from 'v-tooltip';

export default {
    components: { VPopover },

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
