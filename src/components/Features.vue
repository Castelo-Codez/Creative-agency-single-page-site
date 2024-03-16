<script setup></script>
<template>
    <section class="features" aria-label="features section">
        <div aria-label="content wrapper" class="content-wrapper">
            <h1 aria-label="section heading">
                Our approach for creating a winning brand
            </h1>
            <ul role="list" aria-label="features list">
                <li aria-label="feature container" role="listitem">
                    <article aria-label="article about feature">
                        <h2 aria-label="feature name">Brand strategy</h2>
                        <p aria-label="paragraph about feature">
                            Brand strategy is critical for long-term success.
                            Outshining competitors and capturing the target
                            audience are key.
                        </p>
                    </article>
                </li>
                <li aria-label="feature container" role="listitem">
                    <article aria-label="article about feature">
                        <h2 aria-label="feature name">Brand design</h2>
                        <p aria-label="paragraph about feature">
                            Keeping the brand design unique and meaningful helps
                            in communicating the brand’s timeless value
                            effectively.
                        </p>
                    </article>
                </li>
                <li aria-label="feature container" role="listitem">
                    <article aria-label="article about feature">
                        <h2 aria-label="feature name">Web design</h2>
                        <p aria-label="paragraph about feature">
                            A beautifully crafted website is the best tool for
                            brand awareness, and ultimately results in increased
                            revenues.
                        </p>
                    </article>
                </li>
            </ul>
        </div>
    </section>
</template>
<style lang="scss" scoped>
section {
    display: grid;
    grid-template-columns: repeat(7, 1fr);

    grid-template-areas: "cont cont cont cont cont cont cont";
    @media (min-width: 768px) {
        grid-template-areas: ". . . cont cont cont cont";
    }
    .content-wrapper {
        padding: 8vw 7.5vw;
        position: relative;
        @media (min-width: 768px) {
            padding: {
                left: 20vw;
                top: 8vw;
                right: 8vw;
            }
        }
        @media (min-width: 768px) {
            padding-right: 15vw;
            position: relative;
            &::before {
                content: "";
                position: absolute;
                background-color: inherit;
                width: 100%;
                height: 300px;
                left: 0;
                top: -23%;
            }
        }
        background-color: var(--clr-red);
        color: var(--clr-white);
        grid-area: cont;
        --spaces: 6rem;
        h1 {
            line-height: 1.7;
            font-size: 7vw;
            font-weight: 800;
            @media (min-width: 768px) {
                position: absolute;
                top: 43%;
                font-size: 4vw;
                color: var(--clr-text-black);
                left: -50%;
                transform: translateY(-50%);
                max-width: 63%;
            }
        }
        ul {
            margin-top: var(--spaces);
            li {
                margin-bottom: var(--spaces);
                counter-increment: counter;
                h2 {
                    font-weight: 800;
                    font-size: 1.1rem;
                    margin-bottom: 1.3rem;
                    letter-spacing: 1px;
                    & + p {
                        line-height: 1.7;
                        font-weight: 200;
                    }
                }
                position: relative;
                &::before {
                    content: "0" counter(counter);
                    position: absolute;
                    top: -60%;
                    font-size: 5.5rem;
                    left: -1%;
                    font-weight: 700;
                    z-index: 1;
                    color: #ffffff33;
                    @media (min-width: 768px) {
                        left: -12%;
                    }
                }
            }
        }
    }
}
</style>
