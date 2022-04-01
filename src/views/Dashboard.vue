<template>
  <div>
    <HeaderForm />
    <Content />
  </div>
</template>


<script>
  import HeaderForm from '../components/Dashboard/HeaderForm'
  import Content from '../components/Dashboard/Content'
  export default {
    components: {
      HeaderForm,
      Content,
    },
  }
</script>
