<template>
    <core-confirmation class="confirmation"
        v-bind="$attrs"
        v-on="$listeners">
        <template #:default>
            <slot/>
        </template>
        <template #:confirm="{ confirm }">
            <a class="button is-small is-success mr-2"
                @click="confirm">
                <span class="icon is-small">
                    <fa icon="check"/>
                </span>
            </a>
        </template>
        <template #:cancel="{ cancel }">
            <a class="button is-small is-danger"
                @click="cancel">
                <span class="icon is-small">
                    <fa icon="times"/>
                </span>
            </a>
        </template>
    </core-confirmation>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { faCheck, faTimes } from '@fortawesome/free-solid-svg-icons';
import CoreConfirmation from '../components/CoreConfirmation.vue';

library.add(faCheck, faTimes);

export default {
    name: 'Confirmation',

    components: { CoreConfirmation },
};
</script>

<style lang="scss">
    .confirmation > .trigger {
        display: flex !important;
    }
</style>
