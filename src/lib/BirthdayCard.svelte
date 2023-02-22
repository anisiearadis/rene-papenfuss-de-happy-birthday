<script>
    import {marked} from "marked";
    import Cake from "./Cake.svelte";
    import HintCard from "./HintCard.svelte";
    import CodeForm from "./CodeForm.svelte";
    import Image from "./Image.svelte";

    const pages = [
        // COVER
        {
            isCover: true,
            isTurnedOver: false,
            isClickable: true,
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
            isClickable: true,
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

Da ja alles anders gekommen ist als ich geplant hatte und ich teilweise zu ungeduldig war, musste ich etwas umbauen. 😅

Auf den nächsten Seiten erzähle ich nun einfach etwas darüber, was ich geplant hatte und wie es weiter geht. Wenn
du Lust hast mehr davon zu erfahren, dann blätter auf die nächste Seite. 😘
                    `),
                },
            ],
        },
        // Planung 1
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'markdown',
                    content: marked.parse(`
Begonnen hat eigentlich alles damit, dass ich dich an deinem Geburtstag überraschen wollte, indem ich einfach bei dir
vor der Tür stehe. Dann hatte ich gedacht, dass das zwar cool wäre, aber da müsse noch etwas Spaß mit eingebaut werden.

Also habe ich mit dieser Seite angefangen. Ich wollte eine kleine Schnitzeljagd in deiner Wohnung veranstalten. Da
hätte ich in jedem Raum eine Karte versteckt mit Nummern und Hinweisen drauf.

Die hätten dann ungefähr so ausgesehen:
                    `),
                },
            ],
        },
        // Planung 2
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'card',
                },
                {
                    type: 'markdown',
                    content: marked.parse(`
Am Ende hättest du alle Codes in der richtigen Reihenfolge in ein Formular eintragen müssen und dann hättest du gesehen
wo ich mich versteckt halte. Vermutlich wäre ich irgendwo auf deiner Straße gewesen und hätte dort auf dich gewartet. 😅

Desweiteren musste ich bei deinem Geschenk etwas umorganisieren. Eigentlich wollte ich dir ein tolles Bild in ein
Holzbrett gravieren. Dafür war ich dann aber zu ungeschickt und zu zittrig.
                    `),
                },
            ],
        },
        // Planung 3
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'markdown',
                    content: marked.parse(`
Dann hab ich mir gedacht, dass ich doch auch was anderes aus den Brettern machen könnte. Da ist mir eingefallen, dass
ich doch einfach ein paar Dinge ausschneiden und dann auf ein großes Brett kleben könnte. Das habe ich dann letztendlich
gemacht. Ich habe den Entwicklungsprozess etwas dokumentiert. Auf der nächsten Seite findest du ein paar Bilder.
                    `),
                },
            ],
        },
        // Bilder 1
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/001.jpg',
                        originalUrl: '/src/assets/images/001.jpg',
                        caption: 'Die ersten Schnitte sind gemacht.',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/002.jpg',
                        originalUrl: '/src/assets/images/002.jpg',
                        caption: 'Meine Werkzeuge die ich genutzt habe.',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/004.jpg',
                        originalUrl: '/src/assets/images/004.jpg',
                        caption: 'Nicht nur ins Holz habe ich geschnitten.',
                    }
                },
            ],
        },
        // Bilder 2
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/005.jpg',
                        originalUrl: '/src/assets/images/005.jpg',
                        caption: 'Hier ein Bild vom Übeltäter! 🚨',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/006.jpg',
                        originalUrl: '/src/assets/images/006.jpg',
                        caption: 'Hab dann ein Pflaster von Mama bekommen. Das hatte ich zwei Tage getragen.',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/008.jpg',
                        originalUrl: '/src/assets/images/008.jpg',
                        caption: 'Hier die fertig ausgeschnittenen Dinos. 🦕🦕',
                    }
                },
            ],
        },
        // Bilder 3
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/009.jpg',
                        originalUrl: '/src/assets/images/009.jpg',
                        caption: 'Um die Landschaft etwas schöner zu machen, habe ich noch einen Grasstreifen vorbereitet.',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/010.jpg',
                        originalUrl: '/src/assets/images/010.jpg',
                        caption: 'Hier ist er dann auch fertig ausgeschnitten.',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/011.jpg',
                        originalUrl: '/src/assets/images/011.jpg',
                        caption: 'Sieht doch eigentlich schon niedlich aus.',
                    }
                },
            ],
        },
        // Bilder 4
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/012.jpg',
                        originalUrl: '/src/assets/images/012.jpg',
                        caption: 'Etwas mehr Vegetation darf nicht fehlen.',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/014.jpg',
                        originalUrl: '/src/assets/images/014.jpg',
                        caption: 'Ich hab noch ein Bäumchen gebaut. Das kommt auch noch mit drauf.',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/015.jpg',
                        originalUrl: '/src/assets/images/015.jpg',
                        caption: 'Mein Schreibtisch hat auch etwas unter der Aktion gelitten, aber das ist nicht schlimm. 😅',
                    }
                },
            ],
        },
        // Bilder 5
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/016.jpg',
                        originalUrl: '/src/assets/images/016.jpg',
                        caption: 'Jetzt noch etwas Farbe da drauf bringen. 🙈',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/017.jpg',
                        originalUrl: '/src/assets/images/017.jpg',
                        caption: 'Das Malkasten Weiß immer so doof sein muss. Musste dreimal drüber streichen. 🙄',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/018.jpg',
                        originalUrl: '/src/assets/images/018.jpg',
                        caption: 'Nimmt doch Form an.',
                    }
                },
            ],
        },
        // Bilder 6
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: true,
            parts: [
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/019.jpg',
                        originalUrl: '/src/assets/images/019.jpg',
                        caption: 'Natürlich werden die anderen Sachen auch noch angemalt.',
                    }
                },
                {
                    type: 'image',
                    props: {
                        thumbnailUrl: '/src/assets/images/thumbnails/020.jpg',
                        originalUrl: '/src/assets/images/020.jpg',
                        caption: 'Der Himmel ist mir nicht ganz so gelungen. Sollte eigentlich bissl heller sein. 😅',
                    }
                },
                {
                    type: 'markdown',
                    content: marked.parse(`
Das war eine kurze Tour durch meine vergangenen Abende. Das Endergebnis kannst du dir später anschauen. 😅 Ich sags mal
so, sieht aus wie von einem 3-jährigen gebaut, aber es steckt viel Schweiß, Blut und Liebe drin. 🥰😘
                    `),
                },
            ],
        },
        // Schlusswort
        {
            isCover: false,
            isTurnedOver: false,
            isClickable: false,
            parts: [
                {
                    type: 'markdown',
                    content: marked.parse(`
Nun stellst du dir bestimmt die Frage, warum ich diesen Aufwand betrieben habe. Nun, ich wollte dir einfach etwas
basteln. Natürlich habe ich auch noch etwas anderes im Gepäck. 😘 Kannst ja vielleicht mal aus dem Fenster schauen
und gucken, ob ich schon irgendwo rumstehe. 🤭

Ich wünsche dir an dieser Stelle dann mal noch einen schönen Abend und noch ein paar schöne Stunden an deinem
Geburtstag. 🥳🥰😘
                    `),
                },
            ],
        },
    ];

    function movePage(page, forceTurnOver = false) {
        if (!pages[page].isClickable && !forceTurnOver) return;

        pages[page].isTurnedOver = !pages[page].isTurnedOver;
    }
</script>

<div class="d-none d-lg-block birthday-card">
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
                {:else if part.type === 'code-form'}
                    <CodeForm formWasValid={_ => movePage(idx, true)}/>
                {:else if part.type === 'image'}
                    <Image {...part.props}/>
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
    pointer-events: none;
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
    pointer-events: all;

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
