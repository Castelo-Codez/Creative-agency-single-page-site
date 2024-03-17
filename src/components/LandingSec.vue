<script setup>
import PrimaryBtn from "./PrimaryBtn.vue";
</script>
<template>
    <section aria-label="landing section">
        <div class="image-container" aria-label="image wrapper">
            <picture>
                <source
                    media="(min-width: 1200px)"
                    srcset="/desktop/image-hero.webp"
                />
                <source
                    media="(min-width: 768px)"
                    srcset="/tablet/image-hero.webp"
                />
                <img src="/mobile/image-hero.webp" alt="hero image" />
            </picture>
        </div>
        <div aria-label="article wrapper" class="article-container">
            <article>
                <h1 aria-label="main heading">
                    Branding & website design agency
                </h1>
                <p>
                    We specialize in visual storytelling by creating cohesive
                    brand and website design solutions for small businesses,
                    giving lasting impressions to audiences in a digital world.
                </p>
                <PrimaryBtn
                    content="learn more"
                    bgcolor="#f94f4f"
                    hoverbgcolor="#f77171"
                />
            </article>
        </div>
    </section>
</template>
<style scoped lang="scss">
section {
    display: flex;
    max-height: 80vh;
    overflow: hidden;
    flex-direction: column;
    @media (min-width: 768px) {
        flex-direction: row;
        > div:first-child {
            flex-basis: 70%;
            order: 1;
            & + div {
                flex: 1;
            }
        }
    }
    picture {
        display: block;
        img {
            width: 100%;
        }
    }
    .article-container {
        padding: var(--pad-space);
        position: relative;

        h1 {
            font-size: 2.5rem;
            color: var(--clr-text-black);
            font-weight: 800;
            @media (min-width: 768px) {
                font-size: 5rem;
            }
            & + p {
                color: var(--clr-bg-black);
                font-weight: 600;
                line-height: 1.6;
                font-size: 1rem;
                margin-bottom: 28px;
            }
        }
        article {
            @media (min-width: 768px) {
                position: absolute;
                position: absolute;
                top: 11%;
                width: 550px;
                left: 33%;
            }
        }
    }
}
</style>
