<template>
    <div class="menu">
        <router-link to="/">
            <p class="item-menu">
                Home
            </p>
        </router-link>
        <router-link to="/about">
            <p class="item-menu">
                About Us
            </p>
        </router-link>
    </div>
</template>

<style>
    .menu {
        display: flex;
        justify-content: space-around;
    }
</style>