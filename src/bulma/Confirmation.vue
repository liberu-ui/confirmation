<template>
    <base-confirmation v-bind="$attrs"
        v-on="$listeners">
        <template v-slot:default>
            <slot/>
        </template>
        <template v-slot:confirm="{ confirm }">
            <a class="button is-small is-success has-margin-right-medium"
                @click="confirm">
                <span class="icon is-small">
                    <fa icon="check"/>
                </span>
            </a>
        </template>
        <template v-slot:cancel="{ cancel }">
            <a class="button is-small is-danger"
                @click="cancel">
                <span class="icon is-small">
                    <fa icon="times"/>
                </span>
            </a>
        </template>
    </base-confirmation>
</template>

<script>

import { library } from '@fortawesome/fontawesome-svg-core';
import { faCheck, faTimes } from '@fortawesome/free-solid-svg-icons';
import BaseConfirmation from '../components/BaseConfirmation.vue';

library.add(faCheck, faTimes);

export default {
    components: { BaseConfirmation },
};
</script>
