<template>

    <div class="global">
        <div class="skills-description">
            <div v-for="(item, index) in sklls" :key="index" class="skills">
                <h2>{{ item.sklls_name }}</h2>
                <p>{{ item.sklls_description }}</p>
                <p><strong>指令:</strong> {{ item.sklls_command }}</p>
                <img :src="item.img"></img>
                <hr />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SkllsDescription',
    props: {
        sklls: {
            type: Array,
            required: true
        }
    }
}
</script>

<style src="/src/styles/sklls_description.css"></style>