<script>
    let myQuote

    const generateQuote = async () => {
        fetch('https://animechan.xyz/api/random')
        .then(response => response.json())
        .then(quote => myQuote = quote.quote)
    }

    generateQuote()
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
        margin: 0; /* Remove default margin to fill the entire space */
        text-align: center; /* Center-align the text */
        font-size: 48px;
        max-width: 100%; /* Ensure text doesn't overflow horizontally */
        max-height: 100%; /* Ensure text doesn't overflow vertically */
        overflow: hidden; /* Hide overflow text */
    }
</style>