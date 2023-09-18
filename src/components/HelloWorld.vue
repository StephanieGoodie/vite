<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
  <div class="card">
    <img alt="real estate logo" src="./housepic.jpg">
    <div class="card-content"> 
      <h2>Two Pod Realty</h2> 
      <p id="description">Real Estate Company Focused on delivering the best properties in the State College Area</p> 
      <button class="details-button" id="detailsBtn">Details</button>
    </div> 
  </div> 
  
  <button id="btn">Duplicator</button>
  <button id="colorBtn">BGColorChanger</button>
  <button id="Headingbtn">HeadingChanger</button>
  <button id="dltbtn">DeleteCard</button>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  msg: String,
})

const count = ref(0)
</script>

<script>
    document.querySelector('#btn').addEventListener('click', () => {
      const clone = document.querySelector('.card').cloneNode(true); // Clone the whole card
      document.body.appendChild(clone);
    });
    
    var numbers = ["1", "2", "3", "4", "5", "6", "7", "8", "9"];
    var letters = ["A", "B", "C", "D", "E", "F"];
    
    function randomColor() {
      var color = "";
      for (var i = 0; i < 3; i++) {
        var index = Math.floor(Math.random() * (numbers.length + letters.length));
        color += (index < numbers.length) ? numbers[index] : letters[index - numbers.length];
      }
      return color;
    }
    
    document.querySelector('#colorBtn').addEventListener('click', () => {
      const card = document.querySelector('.card');
      // Change background color
      card.style.backgroundColor = '#' + randomColor();
    });
    
    // HEADING CHANGER
    document.querySelector('#Headingbtn').addEventListener('click', () => {
      const title = document.querySelector('h2');
      title.innerText = "Super Pod 2 Realty";
    });
    
    // Card delete
    document.querySelector('#dltbtn').addEventListener('click', () => {
      const cards = document.querySelectorAll('.card');
      // Check if there are cards to delete
      if (cards.length > 1) {
        const lastCard = cards[cards.length - 1];
        lastCard.parentNode.removeChild(lastCard);
      }
    });
    
    var original = document.querySelector('#description').innerText;
    
    document.querySelector('#detailsBtn').addEventListener('click', () => {
      const description = document.querySelector('#description');
      // Toggle the visibility of the description
      if (description.innerText === 'none' || description.innerText === '') {
        description.innerText = original; // Show the description
      } else {
        description.innerText = ''; // Hide the description
      }
    });
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
