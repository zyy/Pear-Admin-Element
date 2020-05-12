<template>
    <div id="main-tab">
       <breadcrumb></breadcrumb>
    </div>
</template>
<script>
import Breadcrumb from "@/components/Breadcrumb";
export default {
    components: {
    Breadcrumb
  },
}
</script>
<style>
#main-tab{
    border-bottom: 1px solid whitesmoke;
    height: 45px;
    padding-left: 15px;
}
</style>