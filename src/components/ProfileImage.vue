<template>
    <img :src="img" class="profile" alt="profile" />
</template>

<script>
export default {
    props: {
        img: {
            type: String
        }
    }
}
</script>