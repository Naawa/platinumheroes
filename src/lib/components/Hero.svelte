<section>
    <img class="hidden" src="/assets/eagleIllustration.png" alt="">
    <div>
        <h1 class="hidden">PLATINUM HEROES</h1>
        <p class="hidden">A community team, home rooted in Starcraft II, with a growing domain into competitive games and beyond.</p>
    </div>
</section>

<style lang="scss">
    section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 8em 10vw;
        gap: 3em;
        background-color: #16202a;
        position: relative;
        overflow: hidden;
        margin: 0 0 1em;
        background-image: url("/assets/sc2blur.png");
        background-size: 200% 200%;
        background-position: center;

        div {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            gap: 1em;
            max-width: 20em;
            min-width: fit-content;

            h1, p {
                color: #e8ecef;
                text-align: center;
            }
        }

        img {
            background-color: transparent;
            max-width: 80vw;
            max-height: 30vh;
            min-width: 200px;
        }
    }
</style>

