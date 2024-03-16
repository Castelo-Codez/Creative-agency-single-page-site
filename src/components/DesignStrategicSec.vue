<template>
    <section aria-label="section tow">
        <div aria-label="image wrapper" class="image-container">
            <picture>
                <source
                    media="(min-width: 1200px)"
                    srcset="/desktop/image-strategic.webp"
                />
                <source
                    media="(min-width: 768px)"
                    srcset="/tablet/image-strategic.webp"
                />
                <img src="/mobile/image-strategic.webp" alt="strategic image" />
            </picture>
        </div>
        <div aria-label="article wrapper" class="article-container">
            <article>
                <h1 aria-label="main heading">
                    <strong>Design</strong> is strategic.
                </h1>
                <p>
                    "A well-crafted design strategy consistently produces
                    desired outcomes and brand awareness. We are firm believers
                    that success lies in creative collaboration with our
                    clients."
                </p>
                <button type="button">Schedule A Call</button>
            </article>
            <div class="pattern" aria-hidden="true">
                <svg width="135" height="61" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M98.882 60.408c10.951 0 19.618-4.864 25.999-14.593 6.38-9.728 9.571-23.054 9.571-39.977h-29.19c-.633 3.439-1.9 6.199-3.8 8.28-1.902 2.082-4.662 3.123-8.283 3.123-3.258 0-6.788-.86-10.59-2.58a354.773 354.773 0 01-12.354-5.905C65.8 6.54 60.89 4.594 55.505 2.92 50.119 1.245 44.214.408 37.787.408c-11.585 0-20.704 4.887-27.356 14.66C3.778 24.843.452 38.1.452 54.843h29.19c.633-3.348 2.059-6.063 4.276-8.144 2.218-2.082 5.182-3.123 8.893-3.123 3.077 0 6.471.838 10.182 2.512a437.483 437.483 0 0112.49 5.905c4.616 2.262 9.708 4.23 15.274 5.905 5.566 1.674 11.608 2.511 18.125 2.511z"
                        fill="#F94F4F"
                        fill-rule="nonzero"
                    />
                </svg>
            </div>
        </div>
    </section>
</template>
<style scoped lang="scss">
section {
    display: grid;
    grid-template-columns: 1fr;
    @media (min-width: 768px) {
        grid-template-columns: 1fr 1fr;
    }
    .image-container {
        picture {
            img {
                width: 100%;
            }
        }
    }
    .article-container {
        position: relative;
        .pattern {
            position: absolute;
            top: -7%;
            @media (min-width: 768px) {
                top: 15%;
                left: -5rem;
            }
        }
        padding: 7.5vw;
        background-color: var(--clr-bg-black);
        color: var(--clr-white);
        article {
            @media (min-width: 768px) {
                max-width: 80%;
            }
        }
        h1 {
            font-size: 2.8rem;
            margin-bottom: 4rem;
            font-weight: 800;
            @media (min-width: 768px) {
                max-width: 50%;
            }
            strong {
                color: var(--clr-red);
            }
            & + p {
                line-height: 2.3;
                font-weight: 300;
                margin-bottom: 4rem;
                & + button {
                    background: none;
                    border: none;
                    color: var(--clr-red);
                    font-size: 1rem;
                    font-weight: 500;
                    position: relative;
                    cursor: pointer;
                    transition: var(--main-transition);
                    z-index: 1;
                    &::after {
                        content: "";
                        position: absolute;
                        width: 100%;
                        bottom: -10px;
                        height: 3px;
                        background-color: var(--clr-red);
                        left: 0;
                        transition: var(--main-transition);
                        z-index: -1;
                    }
                    &:hover {
                        color: var(--clr-white);
                        &::after {
                            height: calc(100% + 10px);
                        }
                    }
                }
            }
        }
    }
}
</style>
