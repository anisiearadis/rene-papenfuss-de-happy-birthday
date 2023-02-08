<script>
    import {marked} from "marked";
    import Cake from "./Cake.svelte";
    import HintCard from "./HintCard.svelte";

    const pages = [
        // COVER
        {
            isCover: true,
            isTurnedOver: false,
            parts: [
                {
                    type: 'markdown',
                    content: marked.parse(`
# Alles Gute zum Geburtstag, Kristin!
                    `),
                },
                {
                    type: 'cake',
                },
            ],
        },
        // GLÜCKWUNSCH
        {
            isCover: false,
            isTurnedOver: false,
            parts: [
                {
                    type: 'markdown',
                    content: marked.parse(`
### Glückwünsche

Hallo mein Schatzi,

ich wünsche dir alles Liebe und Gute zum Geburtstag. Ganz viel

- Glück 🍀
- Erfolg 👍
- Kraft 💪 und
- Gesundheit 💊

im neuen Lebensjahr!

Es tut mir sehr leid, dass ich heute nicht bei dir sein kann. 😔

Trotzdem möchte ich dir ein tolles Geschenk machen und deswegen habe ich mir etwas feines ausgedacht.

Bist du bereit dafür? Wenn ja, dann blätter auf die nächste Seite.
                    `),
                },
            ],
        },
        // Aufgabenbeschreibung
        {
            isCover: false,
            isTurnedOver: false,
            parts: [
                {
                    type: 'markdown',
                    content: marked.parse(`
### Aufgabenbeschreibung

Ok, du willst also bei meinem Spielchen mitmachen. Sehr gut, das freut mich! 😁

Ich habe eine kleine Schnitzeljagd vorbereitet. In jedem Raum in deiner Wohnung habe ich ein Kärtchen versteckt. 🤭

Auf diesen Kärtchen stehen 6-stellige Zahlencodes, die du auf einer der nächsten Seiten eingeben musst. Nur wenn du alle
Zahlenkombinationen richtig eingegeben hast, erfährst du wo sich dein Geschenk befindet. Du kannst natürlich auch extrem
gründlich suchen, aber die Wahrscheinlichkeit auf einen Fund ist sehr gering. 😅

Auf der nächsten Seite findest du die erste Karte. Der Code auf dieser Karte zählt schon und du solltest dir diesen
notieren oder merken.

Ich wünsche dir viel Spaß und Erfolg dabei. 😘
                    `),
                },
            ],
        },
        // ERSTE KARTE
        {
            isCover: false,
            isTurnedOver: false,
            parts: [
                {
                    type: 'markdown',
                    content: marked.parse(`
### Schnitzeljagd

Hier ist die erste Karte:
                    `),
                },
                {
                    type: 'card',
                },
                {
                    type: 'markdown',
                    content: marked.parse(`
Oben siehst du die Nummer der Karte und nach dem Doppelpunkt steht der Code, den du auf der nächsten Seite eingeben
musst. Der untere Teil gibt dir einen Hinweis darauf wo du das nächste Kärtchen findest.

**Wichtig:** Die Reihenfolge der Codes spielt eine Rolle.
                    `),
                },
            ],
        },
    ];

    function movePage(page) {
        pages[page].isTurnedOver = !pages[page].isTurnedOver;
    }
</script>

<div class="birthday-card">
    <div class="birthday-card__instruction">
        Klicke auf die Seiten um zu blättern.
    </div>
    {#each pages as page, idx}
        <div class="birthday-card__page birthday-card__page--front"
             class:birthday-card__page--cover={page.isCover}
             class:birthday-card__page--turned-over="{page.isTurnedOver}"
             on:click={_ => movePage(idx)}>
            {#each page.parts as part}
                {#if part.type === 'markdown'}
                    {@html part.content}
                {:else if part.type === 'cake'}
                    <Cake/>
                {:else if part.type === 'card'}
                    <HintCard/>
                {/if}
            {/each}
        </div>
        <div class="birthday-card__page birthday-card__page--back"
             class:birthday-card__page--turned-over="{page.isTurnedOver}"
             on:click={_ => movePage(idx)}>
        </div>
    {/each}
</div>

<style lang="scss">
  $book-h-ratio: 8.5;
  $book-w-ratio: 5.5;
  $book-size: 77px;

  .birthday-card {
    height: $book-size * $book-h-ratio;
    position: relative;
    transform: perspective(2400px);
    transform-style: preserve-3d;
    width: $book-size * $book-w-ratio * 2;
  }

  .birthday-card__instruction {
    background: #fff7;
    border-radius: 15px;
    color: #0009;
    font-size: 26px;
    left: 25%;
    padding: 10px 15px;
    position: absolute;
    text-align: center;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 300px;
  }

  .birthday-card__page {
    height: $book-size * $book-h-ratio;
    position: absolute;
    right: 0;
    top: 0;
    transform-origin: 0 50%;
    transition: transform 1s;
    width: $book-size * $book-w-ratio;

    &.birthday-card__page--cover {
      background: linear-gradient(#afd2dd, #a1d5e5) 50% 50% / 80% 86% no-repeat,
      linear-gradient(#ffffff, #ffffff) 50% 50% / 90% 93% no-repeat,
      linear-gradient(#9bc8d6, #9bc8d6) no-repeat;
      display: flex;
      flex-direction: column;
      padding: 100px 45px 50px;
      text-align: center;

      & > * {
        flex: 1;
      }
    }
  }

  .birthday-card__page--front {
    background: #eeeeee;
    padding: 50px 45px;
  }

  .birthday-card__page--back {
    background: #e8e8e8;
  }

  @for $i from 1 through 30 {
    .birthday-card__page:nth-child(#{$i}) {
      transform: translatez(-.2px * $i) rotatey(0deg);
    }

    .birthday-card__page--turned-over:nth-child(#{$i}) {
      transform: translatez(.2px * $i) rotatey(-180deg);
    }
  }
</style>
