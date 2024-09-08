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
    margin: 0;
    padding: 0;
  }

  .section {
    background-color: #282828;
    padding-bottom: 10px; /* Minimal padding */
    padding-right: 10px; 
    padding-left: 10px; 
    margin: 15px;
    border-radius: 15px;
    box-shadow: 0 0 20px rgba(0, 128, 255, 0.4); /* Faint blue shadow */
    animation: pulse 2.5s infinite; /* Constant pulsing animation */
  }

  h1, h2, h3, p {
    margin: 5px 0; /* Reduced margin to bring text closer to the top */
    padding: 10px; /* No padding */
    line-height: 1.2; /* Reduced line-height for tighter text */
    text-align: center;
  }

  /* Animation for the box shadow */
  @keyframes pulse {
    0% {
      box-shadow: 0 0 20px rgba(0, 128, 255, 0.4);
    }
    50% {
      box-shadow: 0 0 30px rgba(0, 128, 255, 0.6);
    }
    100% {
      box-shadow: 0 0 20px rgba(0, 128, 255, 0.4);
    }
  }

  /* Grid styling */
  .grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* Flag, arrow, flag layout */
    gap: 10px;
    padding: 0; /* Remove extra padding */
  }

  .grid-item {
    text-align: center;
  }

  .grid-item img {
    width: 250px; /* Increased flag size */
    height: auto;
    border-radius: 10px;
  }

  /* Arrow styling */
  .arrow img {
    width: 250px; /* Adjust arrow size to match flags */
    height: auto;
    margin-top: 30px; /* Fine-tune arrow positioning */
  }

  table {
    width: 70%; /* Increased table width for robotics pictures */
    margin: 20px auto;
    border-collapse: collapse;
    text-align: center;
  }

  table th, table td {
    padding: 10px; /* Increased padding for better spacing */
    border: 1px solid white;
  }

  /* Styling for robotics pictures */
  .robotics-pictures img {
    width: 400px; /* Increased image size */
    height: auto;
    border-radius: 10px;
  }

  /* Center the India flag */
  .india-flag {
    display: flex;
    justify-content: center; /* Center horizontally */
    margin-top: 20px; /* Add some space above */
  }

  .india-flag img {
    width: 250px; /* Adjust flag size */
    height: auto;
    border-radius: 10px;
  }

  /* Center the freeform picture */
  .freeform-picture {
    display: flex;
    justify-content: center; /* Center horizontally */
    margin-top: 20px;
  }

  .freeform-picture img {
    height: 600px; /* Adjust height if needed */
    width: auto;
    border-radius: 10px;
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
      <a href="OCPics.html">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Flag_of_Orange_County%2C_California.svg/1599px-Flag_of_Orange_County%2C_California.svg.png" alt="Orange County Flag">
      </a>
      <p>Born in Orange County - forever my home and friends</p>
    </div>
    <div class="grid-item arrow">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0a/Arrow_White_east.svg/1600px-Arrow_White_east.svg.png" alt="Arrow">
    </div>
    <div class="grid-item">
      <a href="SDPics.html">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Flag_of_San_Diego_Goverment_Variant.svg/1600px-Flag_of_San_Diego_Goverment_Variant.svg.png" alt="San Diego Flag">
      </a>
      <p>San Diego - my new home (not so new, it's been 10 years)</p>
    </div>
  </div>

  <!-- Separate Row for India Flag -->
  <div class="grid-container india-flag">
    <div class="grid-item">
      <a href="IPics.html">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/41/Flag_of_India.svg/1599px-Flag_of_India.svg.png" alt="India Flag">
      </a>
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
  <div class="freeform-picture">
    <img src="https://i.ibb.co/DRW1kwQ/IMG-5502.jpg" alt="Freeform Picture">
  </div>
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
