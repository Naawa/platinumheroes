<script lang="ts">
	import { onMount } from "svelte";
	import { fly } from "svelte/transition";

    let showMenu: boolean = false;
    function toggleMenu() {
        showMenu = !showMenu;
        document.querySelector("button")?.classList.toggle("inactive");
        if(!showMenu) {
            document.body.style.overflowY = "scroll";
        }
        else {
            document.body.style.overflowY = "hidden";
        }
    }

    let animate = false;

    onMount(() => {
        animate = true;
    })
</script>

<nav>
    <a href="/"><img src="/assets/eagleIllustration.png" alt="Logo" class="hidden"></a>
    <button on:click={toggleMenu} class="inactive hidden" >
        <span></span>
        <span></span>
    </button>
    <span class="hidden">
        <a href="#events">Upcoming Events</a>
        <a href="#about">About Us</a>
        <a href="#members">Our Members</a>
        <a href="#join">Join Us</a>
        <a href="#contact">Contact Us</a>
    </span>
</nav>

{#if showMenu}
    <div transition:fly={{ y: 200, duration: 400 }}>
        <a href="#events" on:click={toggleMenu}>Upcoming Events</a>
        <a href="#about" on:click={toggleMenu}>About Us</a>
        <a href="#roster" on:click={toggleMenu}>Our Members</a>
        <a href="#join" on:click={toggleMenu}>Join Us</a>
        <a href="#contact" on:click={toggleMenu}>Contact Us</a>
    </div>
{/if}

<style lang="scss">
    a {
        font-family: "Sofia Sans Extra Condensed", sans-serif;
        font-size: 1.2em;
        img {
            height: 2em;
        }

        &:hover {
            color: #aae4f2;
        }
    }
    nav {
        display: flex;
        justify-content: space-around;
        align-items: center;
        width: 100%;
        height: 4em;
        position: absolute;
        z-index: 8;

        span {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2em;
        }

        button {
            background-color: transparent;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 0.15em;
            flex-direction: column;
            min-width: 2em;
            padding: 0;
            height: 2em;
            width: 2em;
            display: none;

            span {
                width: 2em;
                border: solid 0.15em #c5cfd9;
                border-radius: 10em;
                position: absolute;
                &:first-of-type {
                    width: 1.5em;
                    rotate: 45deg;
                }
                &:last-of-type {
                    width: 1.5em;
                    rotate: -45deg;
                }
            }

            &:hover {
                span {
                    width: 1.5em;
                    border-color: #aae4f2;

                    &:first-of-type {
                        width: 1.5em;
                    }
                }
            }
        }
    }

    .inactive {
        span {
            position: relative;

            &:first-of-type {
                width: 1.25em;
                rotate: 0deg;
            }
            &:last-of-type {
                rotate: 0deg;
                width: 2em;
            }
        }

        &:hover {
            span {
                width: 1.25em;
                &:first-of-type {
                    width: 2em;
                }
            }
        }
    }

    div {
        display: flex;
        flex-direction: column;
        gap: 3em;
        justify-content: center;
        align-items: center;
        position: absolute;
        top: 4em;
        padding: 4em;
        height: calc(100dvh - 4em);
        width: 100%;
        z-index: 2;
        backdrop-filter: blur(6em);
    }

    @media (width < 1200px) {
        a {
            font-size: 1.6em;
        }
        nav {
            justify-content: space-between;
            padding: 0 2em;
            span {
               display: none;
            }
            button {
                span {
                    display: flex;
                }
            }
            button {
                display: flex;
            }
        }
    }
</style>