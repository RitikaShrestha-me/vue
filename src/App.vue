<template>
    <AppHeader />
    <div class="w-full">
        <pet />
    </div>
</template>

<script>
    import AppHeader from './components/AppHeader';
    import pet from './components/pet';

    export default{
        components: { AppHeader, pet },
    };
</script>

<style>
</style>