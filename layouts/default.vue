<template>
    <div class="main-wrapper">
        <div class="main-container">
            <MainHeader />
            <div class="main-content">
                <slot />
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss"> 
@use 'primeflex/primeflex';

.main-wrapper {
    @include primeflex.styleclass('grid');
}

.main-container {
    @include primeflex.styleclass('col-12 md:col-10 md:col-offset-1 lg:col-6 lg:col-offset-3');
}
</style>  