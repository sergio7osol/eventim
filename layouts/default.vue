<template>
    <div class="main-wrapper">
        <div class="main-container">
            <MainHeader />
            <div class="main-content">
                <ul>
                    <li>
                        <nuxt-link :to="{ name: 'index' }">Home</nuxt-link>
                    </li>
                    <li>
                        <nuxt-link :to="{ name: 'details' }">Details</nuxt-link>
                    </li>
                    <li>
                        <nuxt-link :to="{ name: 'details-detail-id', params: { id: 1, desc: 'Text about sheep...' } }">Detail 1</nuxt-link>
                    </li>
                </ul>
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