<template>
    <div>
        <h2 class="text-center">User Id: {{ $route.params.id }}</h2>
    </div>
</template>

<script>
export default {
    validate({params}) {
        return /^\d+$/.test(params.id)
    }
}
</script>
