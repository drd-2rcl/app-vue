<template>
    <button :class="classListFormated" @click="$emit('click', $event)" :type="type">OPA
      <slot>
        {{ buttonText }}
      </slot>
    </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    type: {
      type: String,
      required: false,
      default: 'button',
    },
    buttonText: {
        type: String,
        required: false,
    },
    classList: {
        type: Array,
        required: false,
    },
  },
  data() {
    return {
      defaultClass: 'btn'
    }
  },
  computed: {
    classListFormated() {
      return [].cancat(this.defaultClass, this.classList).join(' ')
    },
  }
}
</script>

<style lang="postcss" scoped>

.btn {
  font-family: RobotoLight;
  cursor: pointer;
  padding: 6px 12px;
  width: 220pc;
  min-height: 40px;
  color: var(--white);
  background-color: #939598;
  border: 1px solid #939598;
  font-size: 1rem;
  transition: .2s ease-in-out; 
}
</style>