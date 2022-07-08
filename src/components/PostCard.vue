<template>
  <div class="card">
    <div class="card-header">
      <div class="card-header-title">
        <slot name="header">{{ title }}</slot>
      </div>
    </div>
    <div class="card-content">
      <slot>{{ body }}</slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ['title', 'body'],
}
</script>