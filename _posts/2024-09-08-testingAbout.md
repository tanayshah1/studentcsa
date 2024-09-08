---
layout: page
title: Testing About Me Page
type: issues
--- 

<style>
  body {
    background-color: #1a1a1a; /* Dark background */
    color: white; /* White font */
    font-family: 'Helvetica Neue', sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
  }

  .section {
    background-color: #282828;
    padding: 20px;
    margin: 20px;
    border-radius: 15px;
    box-shadow: 0 0 20px rgba(0, 128, 255, 0.4); /* Faint blue shadow */
    animation: pulse 2.5s infinite; /* Constant pulsing animation */
  }

  @keyframes pulse {
    0% {
      box-shadow: 0 0 20px rgba(0, 128, 255, 0.4);
    }
    50% {
      box-shadow: 0 0 30px rgba(0, 128, 255, 0.6); /* Increase intensity */
    }
    100% {
      box-shadow: 0 0 20px rgba(0, 128, 255, 0.4); /* Return to normal */
    }
  }

  h1, h2, h3, p {
    text-align: center;
    padding: 10px;
  }

  /* Grid styling */
  .grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    padding: 20px;
  }

  .grid-item {
    text-align: center;
    padding: 20px;
  }

  .grid-item img {
    width: 100%;
    height: auto;
    border-radius: 10px;
  }

  /* Add pulsing shadow to grid items as well */
  .grid-item {
    box-shadow: 0 0 15px rgba(0, 128, 255, 0.4);
    animation: pulse 2.5s infinite;
  }

  table {
    width: 50%;
    margin: 20px auto;
    border-collapse: collapse;
    text-align: center;
  }

  table th, table td {
    padding: 10px;
    border: 1px solid white;
  }

  /* Arrow styling (Bigger size, no pulse) */
  .arrow img {
    width: 200px; /* Adjust to be similar in size to the flags */
    height: auto;
    margin-top: -20px;
    /* No pulsing effect for the arrow */
    box-shadow: none;
  }

</style>

<div class="section">
  <h1>Tanay Shah's Webpage</h1>
  <p>This is my CSA website. Learn more about me.</p>
</div>

<div class="section">
  <h2>About Me</h2>
  <p>
    I am a junior at Del Norte High School. I am an 11th grader at Del Norte High School in San Diego.
    While other 4-year-olds wanted to be Superman or Spiderman, I wanted to be "All The Mans"!
  </p>
  <p>
    This thirst for trying and learning new things has led me to tinker with various interests ranging
    from robotics to hip-hop dance to piano (that last one didn't quite pan out :) ). I have won several
    State and Regional awards with FIRST Lego League, VexIQ, and FIRST Tech Challenge robotics competitions 
    and have been invited to be a keynote speaker for Altitude Learning and the D39X Educational Summit.
  </p>
</div>

<div class="section">
  <h2>Who Am I?</h2>
  <p>
    I was born in Orange County, CA, and then moved to San Diego when I was 7 years old. I am an Indian American;
    my parents were born in Mumbai, India, and then immigrated here. I was raised with Indian roots, traditions, 
    and customs, and I love everything about it. I often say, "I'm Indian American, Indian first."
  </p>

  <!-- Grid with Arrow Between Orange County and San Diego -->
  <div class="grid-container">
    <div class="grid-item">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Flag_of_Orange_County%2C_California.svg/1599px-Flag_of_Orange_County%2C_California.svg.png" alt="Orange County Flag">
      <p>Born in Orange County - forever my home and friends</p>
    </div>
    <div class="grid-item arrow">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0a/Arrow_White_east.svg/1600px-Arrow_White_east.svg.png" alt="Arrow">
    </div>
    <div class="grid-item">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Flag_of_San_Diego_Goverment_Variant.svg/1600px-Flag_of_San_Diego_Goverment_Variant.svg.png" alt="San Diego Flag">
      <p>San Diego - my new home (not so new, it's been 10 years)</p>
    </div>
  </div>

  <!-- Separate Row for India Flag -->
  <div class="grid-container">
    <div class="grid-item">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/41/Flag_of_India.svg/1599px-Flag_of_India.svg.png" alt="India Flag">
      <p>Indian American but India first</p>
    </div>
  </div>
</div>

<div class="section">
  <h2>Robotics Pictures</h2>
  <table>
    <tr>
      <td><img src="https://i.ibb.co/VVCc0M3/IMG-5455-1.jpg" alt="Robots"></td>
      <td><img src="https://i.ibb.co/4sR7S69/20230815-192023.jpg" alt="Awards"></td>
    </tr>
    <tr>
      <td>Me with several robots I've built.</td>
      <td>Several awards I've won in robotics.</td>
    </tr>
  </table>
</div>

<div class="section">
  <h2>My Freeform Picture</h2>
  <img src="https://i.ibb.co/DRW1kwQ/IMG-5502.jpg" width="auto" height="600px" alt="Freeform Picture">
  <p>This is the freeform picture that I created, representing my family and my mixed cultural heritage.</p>
</div>

<div class="section">
  <h2>My Class Schedule</h2>
  <table>
    <tr>
      <th>Period</th>
      <th>Class</th>
    </tr>
    <tr>
      <td>1</td>
      <td>AP CSA</td>
    </tr>
    <tr>
      <td>2</td>
      <td>APEL</td>
    </tr>
    <tr>
      <td>3</td>
      <td>United States History</td>
    </tr>   
    <tr>
      <td>4</td>
      <td>AP Bio</td>
    </tr>
    <tr>
      <td>5</td>
      <td>AP Physics</td>
    </tr>
  </table>
</div>
