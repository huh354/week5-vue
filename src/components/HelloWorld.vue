<template>
<div class = "wrapper">
<div class = "card">
<div class = "header">

  <h1>Welcome to my card</h1>
  </div>

  <img src="https://cdn.creatureandcoagency.com/uploads/2021/03/FrogLifecycle_Body_8.png">
 
  <div class = "paragraph">
  <p>This is a picture of a frog that I fond on the internet. It looks really cool and I thought it would be nice to share.</p>
  </div>

<div class="btn-wrapper">
 <a href="https://hax.psu.edu">
   <button>Details</button> </a> </div>
  </div>
  </div>


</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
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
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.color {
  background-color: red;
}
body {
  background-color: lightgreen;
  
}
.card { 
  border-style: solid;
  border-width: 3px;
  border-color: green;
  border-radius: 10px;
  width: 450px;
}
img {
  margin: 25px;
  width: 400px;
  height: auto;
}
.btn-wrapper {
  margin: 24px;
}
.btn-wrapper button {
  font-size: 24px;
  color: green;
  background-color: white;
}
.btn-wrapper button:hover {
  color: white;
  background-color: green;
}
.header {
  font-size: 20px;
  margin: 25px;
}
.paragraph {
  font-size: 20px;
  margin: 25px;
}
@media screen and (max-width: 800px) {  
  div.Frog {
    display: none;
  }
  div.header{
    display: none;
  }
  div.paragraph{
    display: none;
  }

}
div, span {
  display: inline-block;
}


</style>
