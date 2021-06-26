<template>
    <tabs>
        <tab name="First">
            <p>Test</p>
        </tab>
        <tab name="Sercond">
            <ul>
                <li>Alo</li>
            </ul>
        </tab>
        <tab name="Third">
            <alert type="danger">Thisalert</alert>
        </tab>
    </tabs>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
    setup() {
        
    },
})
</script>
