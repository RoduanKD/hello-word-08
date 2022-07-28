<template>
  <section class="section">
    <div class="container">
      <div class="columns">
        <div class="column is-desktop-3"><img src="@/assets/Picture1.png" alt="Roduan Kareem Aldeen"></div>
        <div class="column">
          <div class="title is-3">{{ name || 'Roduan Kareem ALdeen' }}</div>
          <div class="content">
            {{ description || 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Placeat tenetur excepturi similique, cupiditate atque rerum quisquam porro eius laborum facere!' }}
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['name', 'description']
}
</script>