<template>
    <div class="menber_wrapper">
        <img class="photo" :src="Members.image" alt="" :style="Members.style">
        <div class="text">
            <h2>{{ Members.name }}</h2>
            <h4>{{ Members.age }} 세</h4>
            <p>{{ Members.content }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name : 'NewJeans',
    props: {
        Members : Array,
    }
}
</script>