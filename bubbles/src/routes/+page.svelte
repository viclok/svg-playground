<script>
    import { onMount } from 'svelte';
    let myQuote

    let anime_quotes = ["I’m not gonna run away, I never go back on my word! That’s my nindo: my ninja way!",
    "A smile is the easiest way out of a difficult situation.",
    "Hard work is worthless for those that don’t believe in themselves.",
    "When people are protecting something truly precious to them, they truly can become as strong as they need to be!",
    "I won’t run away anymore… I won’t go back on my word… that is my ninja way!",
    "I’m not gonna let myself get beaten down anymore. I’m gonna be the best!",
    "While you’re alive, you need a reason for your existence. Being unable to find one is the same as being dead.",
    "I care more about others than I do myself, and I won’t let anyone hurt them.",
    "The true measure of a shinobi is not how he lives but how he dies.",
    "I will become a stronger fighter! I will surpass everyone who has come before me!",
    "The difference between insanity and genius is measured only by success and failure.",
    "When you give up, your dreams and everything else, they’re gone.",
    "Once you question your own belief, it’s over.",
    "There’s only one thing that can heal the heart… only one… It’s love.",
    "My friends were the first to accept me for who I am.",
    "If you don’t like your destiny, don’t accept it. Instead, have the courage to change it the way you want it to be.",
    "The concept of hope is nothing more than giving up. A word that holds no true meaning.",
    "Sasuke… I always knew you were alone. In the beginning, I was glad because I thought you were like me… But… but as I got to know you… I realized… you were just lonely.",
    "The next generation will always surpass the previous one. It’s one of the never-ending cycles in life.",
    "It’s foolish to fear what we’ve yet to see and know.",
    "Because they saved me from myself, they rescued me from my loneliness.",
    "There’s no advantage to hurrying through life.",
    "Home is where someone is always thinking of you.",
    "People cannot win against their loneliness because loneliness is this world’s worst kind of pain.",
    "I have long since closed my eyes… My only goal is in the darkness.",
    "In the ninja world, those who break the rules are trash. But those who abandon their friends are even worse than trash.",
    "It’s not the face that makes someone a monster, it’s the choices they make with their lives.",
    "In order to survive, we cling to all we know and understand. And label it reality.",
    "My first impression of Konoha was… certainly nothing compared to how I feel now. Then, I really wanted to destroy it."
    // "I am not alone. Do not underestimate humans.",
    // "No one knows what the future holds. That's why its potential is infinite.",
    // "Even if we forget the faces of our friends, we will never forget the bonds that were carved into our souls.",
    // "People die if they are killed.",
    // "If you can't find a reason to fight, then you shouldn't be fighting.",
    // "Whatever you lose, you'll find it again. But what you throw away you'll never get back.",
    // "If you wanna make people dream, you've gotta start by believing in that dream yourself!",
    // "There's no hope on the battlefield. It has nothing but unspeakable despair.",
    // "People's lives don't end when they die, it ends when they lose faith.",
    // "If you can't do something, then don't. Focus on what you can.",
    // "Being weak is nothing to be ashamed of... Staying weak is!",
    // "It’s okay not to be okay as long as you are not giving up.",
    // "No matter how deep the night, it always turns to day, eventually.",
    // "It’s not the face that makes someone a monster, it’s the choices they make with their lives.",
    // "It's not the face that makes someone a monster, it's the choices they make with their lives.",
    // "It is okay to live. It is okay to live.",
    // "The future is always blank. Only your willpower can leave footsteps."
]


    // const generateQuote = async () => {
    //     fetch('https://animechan.xyz/api/random')
    //     .then(response => response.json())
    //     .then(quote => myQuote = quote.quote)
    // }

    const generateQuote = () => {
        let min = Math.ceil(0); // Round up to the nearest integer
        let max = Math.floor(anime_quotes.length); // Round down to the nearest integer
        myQuote = anime_quotes[Math.floor(Math.random() * (max - min + 1)) + min];
    }

    onMount(() => {
        generateQuote()
    });
</script>

<div class="hello">
    <div class="quote-box">
        <p>{myQuote}</p>
    </div>

    <button class="gen-button" on:click={generateQuote}>Generate new MLK quote</button>
</div>


<style>
    .hello {
        width: 100vw;
        height: 100vh;
        background-image: url($lib/images/mlk.jpg);
        background-repeat: no-repeat;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover; 
    }

    .gen-button {
        position: absolute;
        top: 50%;
        left: 5%;
        width: 50%;
        height: 10%;
        font-size: 40px;
    }

    .quote-box {
        background-color: white;
        position: absolute;
        width: 50%;
        height: 60%;
        top: 5%;
        left: 5%;
        display: flex;
        justify-content: center; /* Horizontal centering */
        align-items: center; /* Vertical centering */
        height: 400px; /* Set a height for the container */
        border: 1px solid #ccc; /* Optional: Add a border for visualization */
    }

    p {
        margin: 5px; /* Remove default margin to fill the entire space */
        text-align: center; /* Center-align the text */
        font-size: 2vw;
        max-width: 100%; /* Ensure text doesn't overflow horizontally */
        max-height: 100%; /* Ensure text doesn't overflow vertically */
        overflow: hidden; /* Hide overflow text */
    }
</style>