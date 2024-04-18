<template>
    <article :class="['message', variant]">
      <div class="message-header">
        <p>{{ title }}</p>
        <button class="delete" aria-label="delete" @click="closeMessage"></button>
      </div>
      <div class="message-body">
        {{ messageContent }}
      </div>
    </article>
  </template>
  
  <script>
  export default {
    props: {
      variant: {
        type: String,
        default: "is-primary",
        validator: function(value) {
          return [
            "is-primary",
            "is-link",
            "is-info",
            "is-success",
            "is-warning",
            "is-danger"
          ].includes(value);
        }
      },
      title: {
        type: String,
        default: ""
      },
      message: {
        type: String,
        default: null
      }
    },
    computed: {
      messageContent() {
        if (this.message === null || this.message.trim() === '') {
          return "Add some text here";
        } else {
          return this.message;
        }
      }
    },
    methods: {
      closeMessage() {
        this.$emit("close");
      }
    }
  };
  </script>