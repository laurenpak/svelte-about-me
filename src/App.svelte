<!-- The "javscript": the functionality -->
<script>
  import ImageCard from "./lib/ImageCard.svelte";

  let cardData = [
    {
      image:
        "https://img.decrypt.co/insecure/rs:fit:3840:0:0:0/plain/https://cdn.decrypt.co/wp-content/uploads/2023/12/dogwifhat-market-gID_7.png@webp",
      title: "staring at stocks",
      description: "Exactly what it says. (jk I don't own any stocks)",
    },
    {
      image:
        "https://media.istockphoto.com/id/1334933890/photo/dog-pretending-to-be-a-chef.jpg?s=612x612&w=0&k=20&c=rknZWcq4vVMN2F5HeYoM7esPysJO59icrady8nyyzsM=",
      title: "attempting to cook",
      description: "I almost burnt my house down with instant mac and cheese",
    },
    {
      image:
        "https://www.allthingsdogs.com/wp-content/uploads/2019/06/Dog-Memes-Feature-678x381.jpg",
      title: "cooking up some code",
      description: "But also taking a 1-hour break after 10 minutes",
    },
  ];

  let name = "Lauren"; // Change this to your name
  let age = 19; // Change this to your age
  let bio = `<p>I am a rising college junior! <br> I love KWK 💚 <br>#live #laugh #love</p>`;
  let hobbies = [
    "Coding",
    "Reading",
    "Photography",
    "Digital Art",
    "Watching Movies",
    "Cafe Hopping",
  ]; // List some hobbies
  let randomColor = [
    "#E6BCC6",
    "#97C9E0",
    "#A8D9C3",
    "#E4D3AD",
    "#CCAADD",
    "#F9D67A",
    "#BCE2CB",
  ];
  let randDigit = Math.floor(Math.random() * 7);
</script>

<!-- the HTML: displays the content -->
<div class="container">
  <h1 style="color: {randomColor[randDigit]}">hello world!</h1>
  <span>My name is</span>
  <span style="color: {randomColor[randDigit]}"><strong>{name}</strong></span>
  <p>I am <em>{age}</em> years old.</p>
  <p>{@html bio}</p>

  <img
    style="border-color: {randomColor[randDigit]}"
    src="svelte-about-me/public/photo.jpeg"
    alt="lauren and her coffee"
    width="30%"
  />

  <h2 style="padding-top: 15px; color: {randomColor[randDigit]}">My Hobbies</h2>
  <div class="hobbies">
    {#each hobbies as hobby}
      <div class="hobby" style="background-color: {randomColor[randDigit]}">
        {hobby}
      </div>
    {/each}
  </div>
  <p>... and more!</p>

  <h2 style="padding-top: 20px; color: {randomColor[randDigit]}">
    Some of My Favorite Things
  </h2>
</div>

<div class="card-container" style="display: inline-block;">
  {#each cardData as { image, title, description }}
    <ImageCard {image} {title} {description} />
  {/each}
</div>

<!-- the CSS: the page styling -->
<style>
  h1 {
    color: #2c3e50;
    font-family: "Courier New", Courier, monospace;
  }
  .container {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
    font-family: "Courier New", Courier, monospace;
  }
  .hobbies {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
  }
  .hobby {
    /* background-color: #3498db; */
    color: white;
    padding: 10px 15px;
    border-radius: 5px;
  }
  img {
    border-style: solid;
    border-width: 5px;
  }
</style>
