<!-- src/lib/ImageCard.svelte -->

<script>
    export let image;  // Image URL prop
    export let title;  // Title prop
    export let description;  // Description prop
  </script>
  
  <style>

    .card {
      display: inline-block;
      background-color: #fff;
      border: 1px solid #ddd;
      border-radius: 10px;
      overflow: hidden;
      width: 200px;
      height: 300px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      margin: 20px;
      text-align: center;
      font-family: "Courier New", Courier, monospace;
    }
  
    .card img {
      display: inline-block;
      width: 100%;
      height: 120px;
      object-fit: cover;
      /* height: 100%; */
    }
  
    .card-content {
      display: inline-block;
      padding: 15px;
      display: inline-block;
    }
  
    .card-title {
      font-size: 1.5em;
      color: #333;
      margin: 0 0 10px 0;
    }
  
    .card-description {
      font-size: 1em;
      color: #666;
      margin: 0;
    }
  </style>
  
  <div class="card">
    <img src={image} alt={title} />
    <div class="card-content">
      <h2 class="card-title">{title}</h2>
      <p class="card-description">{description}</p>
    </div>
  </div>
  