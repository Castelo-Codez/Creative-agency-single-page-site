<script setup>
import {computed, ref} from "vue";

const $currentIndex = ref(1);
const $arrayOfel = ref([
    "Brand naming & guidelines",
    "Brand identity & merchandise",
    "Brand identity & web design",
]);
const $arrayOfArticles = ref([
    {
        heading: "Lean Product Roadmap",
        para: "2019 Project",
    },
    {
        heading: "New Majestic Hotel",
        para: "2018 Project",
    },
    {
        heading: "Crypto Dashboard",
        para: "2016 Project",
    },
]);

const $currentHeading = computed(() => {
    if ($currentIndex.value > $arrayOfel.value.length) {
        $currentIndex.value = 1;
    }
    if ($currentIndex.value < 1) {
        $currentIndex.value = $arrayOfel.value.length;
    }
    return $arrayOfel.value[$currentIndex.value - 1];
});
const $currentArticle = computed(() => {
    if ($currentIndex.value > $arrayOfArticles.value.length) {
        $currentIndex.value = 1;
    }
    if ($currentIndex.value < 1) {
        $currentIndex.value = $arrayOfArticles.value.length;
    }
    return $arrayOfArticles.value[$currentIndex.value - 1];
});
</script>
<template>
    <section aria-label="slide show section">
        <div aria-label="section of images" class="image-wrapper">
            <ul
                role="list"
                :style="{
                    transform: `translateX(-${$currentIndex - 1}00%)`,
                }"
            >
                <li aria-label="image container" role="listitem">
                    <picture>
                        <source
                            media="(min-width: 1200px)"
                            srcset="/desktop/image-slide-1.webp"
                        />
                        <source
                            media="(min-width: 768px)"
                            srcset="/tablet/image-slide-1.webp"
                        />
                        <img src="/mobile/image-slide-1.webp" alt="image 1" />
                    </picture>
                </li>
                <li aria-label="image container" role="listitem">
                    <picture>
                        <source
                            media="(min-width: 1200px)"
                            srcset="/desktop/image-slide-2.webp"
                        />
                        <source
                            media="(min-width: 768px)"
                            srcset="/tablet/image-slide-2.webp"
                        />
                        <img src="/mobile/image-slide-2.webp" alt="image 2" />
                    </picture>
                </li>
                <li aria-label="image container" role="listitem">
                    <picture>
                        <source
                            media="(min-width: 1200px)"
                            srcset="/desktop/image-slide-3.webp"
                        />
                        <source
                            media="(min-width: 768px)"
                            srcset="/tablet/image-slide-3.webp"
                        />
                        <img src="/mobile/image-slide-3.webp" alt="image 3" />
                    </picture>
                </li>
            </ul>
            <article aria-label="projects" :key="$currentArticle">
                <h4 aria-label="project name">{{ $currentArticle.heading }}</h4>
                <p aria-label="about project">{{ $currentArticle.para }}</p>
            </article>
        </div>
        <div aria-label="controllers" class="controllers">
            <h3 :key="$currentIndex">{{ $currentHeading }}</h3>
            <ul aria-label="controllers list" role="list">
                <li role="listitem" aria-label="controller">
                    <button
                        type="button"
                        aria-label="click to previous element"
                        @click="$currentIndex--"
                    >
                        <svg
                            width="40"
                            height="40"
                            xmlns="http://www.w3.org/2000/svg"
                        >
                            <g
                                transform="matrix(-1 0 0 1 40 0)"
                                stroke="#F94F4F"
                                fill="none"
                                fill-rule="evenodd"
                            >
                                <circle cx="20" cy="20" r="19.5" />
                                <path stroke-width="2" d="M17.5 15l5 5-5 5" />
                            </g>
                        </svg>
                    </button>
                </li>
                <li role="listitem" aria-label="controller">
                    <button
                        type="button"
                        @click="$currentIndex++"
                        aria-label="click to next element"
                    >
                        <svg
                            width="40"
                            height="40"
                            xmlns="http://www.w3.org/2000/svg"
                        >
                            <g stroke="#F94F4F" fill="none" fill-rule="evenodd">
                                <circle cx="20" cy="20" r="19.5" />
                                <path stroke-width="2" d="M17.5 15l5 5-5 5" />
                            </g>
                        </svg>
                    </button>
                </li>
            </ul>
        </div>
        <div aria-label="pattern" class="pattern">
            <svg width="134" height="60" xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M98.43 0c10.951 0 19.618 4.864 25.999 14.593C130.809 24.32 134 37.647 134 54.57h-29.19c-.633-3.439-1.9-6.199-3.8-8.28-1.902-2.082-4.662-3.123-8.283-3.123-3.258 0-6.788.86-10.59 2.58a354.77 354.77 0 00-12.354 5.905c-4.435 2.217-9.345 4.162-14.73 5.837C49.667 59.163 43.762 60 37.335 60 25.75 60 16.631 55.113 9.98 45.34 3.326 35.565 0 22.307 0 5.565h29.19c.633 3.348 2.059 6.063 4.276 8.144 2.218 2.082 5.182 3.123 8.893 3.123 3.077 0 6.471-.838 10.182-2.512a437.497 437.497 0 0012.49-5.905c4.616-2.262 9.708-4.23 15.274-5.905C85.871.837 91.913 0 98.43 0z"
                    fill="#FFF"
                    fill-rule="nonzero"
                />
            </svg>
        </div>
    </section>
</template>
<style scoped lang="scss">
section {
    position: relative;
    display: grid;
    grid-template-columns: 1fr;
    @media (min-width: 768px) {
        grid-template-columns: repeat(7, 1fr);
        grid-template-areas: ". . . cont cont cont cont";
    }
    .image-wrapper {
        overflow: hidden;
        position: relative;
        @media (min-width: 768px) {
            grid-area: cont;
        }
        > article {
            position: absolute;
            bottom: 7%;
            width: 230px;
            color: white;
            z-index: 11111;
            right: 7%;
            text-align: right;
            animation: move var(--main-transition);
            @keyframes move {
                0% {
                    transform: translateX(50px);
                    opacity: 0;
                }
                100% {
                    transform: translateX(0);
                    opacity: 1;
                }
            }
            h4 {
                margin-bottom: 0.5rem;
                font-size: 1.2rem;
                font-weight: 700;
                letter-spacing: 1px;
                & + P {
                    color: var(--clr-white);
                    font-size: 0.8rem;
                    font-weight: 300;
                    font-size: 1rem;
                }
            }
        }
        ul {
            display: flex;
            transition: var(--main-transition);
            li {
                position: relative;
                flex-shrink: 0;
                flex-basis: 100%;
                &::after {
                    content: "";
                    position: absolute;
                    width: 100%;
                    height: 15%;
                    bottom: 0;
                    background-image: linear-gradient(
                        180deg,
                        rgba(255, 255, 255, 0),
                        #020202eb
                    );
                }
                picture {
                    display: block;
                    width: 100%;
                    img {
                        width: 100%;
                        max-height: 100%;
                    }
                }
            }
        }
    }
    .controllers {
        padding: var(--pad-space);
        @media (min-width: 768px) {
            padding: 8vw 10vw 8vw 15vw;
        }
        background-color: black;
        h3 {
            color: var(--clr-white);
            font-size: 2rem;
            @media (min-width: 768px) {
                font-size: 3.5vw;
            }
            font-weight: 700;
            line-height: 1.5;
            position: relative;
            animation: show var(--main-transition);

            @keyframes show {
                0% {
                    opacity: 0;
                    transform: translateY(-40px);
                }
                100% {
                    opacity: 1;
                    transform: translateY(0);
                }
            }
            & + ul {
                display: flex;
                margin-top: 2rem;
                column-gap: 1rem;

                li {
                    button {
                        background: none;
                        border: none;
                        cursor: pointer;
                    }
                }
            }
        }
        @media (min-width: 768px) {
            position: absolute;
            width: 53%;
            min-height: 30%;
        }
    }
    .pattern {
        position: absolute;
        left: 55%;
        transform: translateX(-80%);
        top: 20%;
        display: none;
        @media (min-width: 768px) {
            display: block;
        }
    }
}
</style>
