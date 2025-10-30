<template>
  <button :class="$style.button" :data-layout="props.layout" :disabled="props.isDisabled" :type="props.type">
    <slot></slot>
  </button>
</template>

<script setup lang="ts">
interface IProps {
  layout?: 'primary' | 'secondary';
  type?: 'submit' | 'button';
  isDisabled?: boolean;
}

const props = withDefaults(defineProps<IProps>(), {
  layout: 'primary',
  type: 'button',
});
</script>

<style module lang="scss">
.button {
  display: inline-flex;
  gap: 8px;
  align-items: center;
  justify-content: center;
  height: 40px;
  padding: 0 24px;
  font-family: monospace;
  font-size: 1rem;
  color: var(--color-white);
  background: var(--color-primary);
  border: none;
  border-radius: 6px;

  &[data-layout='secondary'] {
    color: var(--color-primary);
    background: transparent;
    border: 1px solid var(--color-primary);
  }
}
</style>
