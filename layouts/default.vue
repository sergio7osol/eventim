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
    @include primeflex.styleclass('col-6 col-offset-3');
}
</style>  