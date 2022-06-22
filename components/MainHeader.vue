<template>
    <header class="main-header">
        <div class="site-logo">
            <nuxt-link :to="{ name: 'index' }" class="site-logo__link" title="Go to Home page">
                <picture>
                    <source srcset="/images/atelier-theater-logo.webp" type="image/webp">
                    <img class="site-logo__pic" src="/images/atelier-theater-logo.png" width="176" height="36" alt="Atelier Theater Köln" loading="lazy" />
                </picture>
            </nuxt-link>
        </div>
    </header>
</template>

<style lang="scss">
.site-logo {
    &__pic {
        width: 11rem;
        height: auto;
    }
}
</style>