<template>
    <div>
        <message variant="is-info" title="Info Message" @close="closeMessage">
        MIAAAU :3
    </message>
    <Message variant="is-warning" title="Warning Message" @close="closeMessage">
        MIAAAAAAAU
    </Message>
    <message variant="is-info" title="Error Message" @close="closeMessage">
        miau
    </message>
    </div>
</template>

<script>
import Message from "./App.vue";

export default {
    components: {
        Message
    },
    methods: {
        closeMessage() {
            console.log("jah kadunud");
        }
    }
};
</script>