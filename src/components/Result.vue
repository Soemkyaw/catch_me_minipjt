<template>
    <h3>You catch me in {{ score }}ms</h3>
    <div v-if="score<250">
        <h3 class="tooFast">Oh My God!!! Your are too fast 😮😮😮</h3>
    </div>
    <div v-else-if="score > 250 && score < 400">
        <h3 class="fast">Your are fast 🫡🫡🫡</h3>
    </div>
    <div v-else>
        <h3 class="slow">LOL Your are too slow, Try again 😫😫😫</h3>
    </div>
</template>

<script>
export default {
    name,
    props: ['score'],
}
</script>

<style>
    .tooFast{
        color: rgb(34, 215, 34);
        margin-top: 10px;
    }
    .fast{
        color: rgb(17, 164, 223);
        margin-top: 10px;
    }
    .slow{
        color: rgb(215, 30, 30);
        margin-top: 10px;
    }
</style>