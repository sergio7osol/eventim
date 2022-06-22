<template>
    <div class="main-wrapper">
        <div class="main-container">
            <header class="">
                <img class="site-logo" src="/assets/images/eventim-logo.webp" alt="Atelier Theater Köln" loading="lazy">
            </header>
        </div>
    </div>
</template>

<style scoped lang="scss">
@import 'primeflex/primeflex.scss';

.main-wrapper {
    @include styleclass('grid');
}

.main-container {
    @include styleclass('col-6 col-offset-3');
}

.site-logo {
    width: 11rem;
}
</style>  