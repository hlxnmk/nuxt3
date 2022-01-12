<script setup lang="ts">

</script>

<template>
    <div>
        <h2>Home组件内容</h2>
        <div>
            <ul class="nav nav-tabs">
                <li>
                    <NuxtLink class="list-group-item" active-class="active" to="/home/news">News</NuxtLink>
                </li>
                <li>
                    <NuxtLink class="list-group-item" active-class="active" to="/home/message">Message</NuxtLink>
                </li>
            </ul>
            <br />
            <NuxtChild />
        </div>
    </div>
</template>

