<template>
  <div>
  <div v-if="showDiv1" class="mainpage">
    <video autoplay muted loop id="money">
      <source src="money.mp4" type="video/mp4">
      Your browser does not support HTML5 video.
    </video>

    <div class="covers">
      <img src="TheDarkSide.png" style="width:330px;height:330px;">
        <p class="text">The Dark Side Of The Moon (1973)</p>
    </div>

    <div class="covers">
      <img src="Animals.jpg" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">Animals (1977)</p>
    </div>

    <div class="covers">
      <img src="AtomHeart.png" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">Atom Heart Mother (1970)</p>
    </div>

    <div class="covers">
      <img src="ThePiper.jpg" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">The Piper at the Gates of Dawn (1967)</p>
    </div>

    <div class="covers">
      <img src="TheWall.png" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">The Wall (1979)</p>
    </div>

    <div class="covers">
      <img src="WishYouWereHere.png" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">Wish You Were Here (1975)</p>
    </div>

    <div class="covers">
      <img src="amomentarylapse.jpg" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">A Momentary Lapse of Reason (1987)</p>
    </div>

    <div class="covers">
      <img src="meddle.png" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">Meddle (1971)</p>
    </div>

    <div class="covers">
      <img src="TheDivision.png" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">The Division Bell (1994)</p>
    </div>

    <div class="covers">
      <img src="thefinalcut.png" alt="HTML tutorial" style="width:330px;height:330px;">
      <p class="text">The Final Cut (1983)</p>

    </div>
    </div>


    <div v-if="!showdiv1" class="bestellen">
    <h2>Form</h2>
    <form>
      <div>
        <label for="name">Name:</label>
        <input type="text" id="name" v-model="name" />
      </div>
      <div>
        <label for="age">Age:</label>
        <input type="number" id="age" v-model="age" />
      </div>
      <div>
    <label>Choose:</label>
    <select v-model="selectedOption">
      <option v-for="option in options" :key="option">{{ option }}</option>
    </select>
  </div>
      <div>
        <label for="country">Country:</label>
        <input type="text" id="country" v-model="country" />
      </div>
      <div>
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" />
      </div>
      <div>
        <button @click.prevent="submitForm" class="submit">Submit</button>
      </div>
    </form>
  </div>
<button @click="showDiv1 = !showDiv1">>Bestellen</button>
</div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      age: "",
      country: "",
      email: "",
      showDiv1: true,
      selectedOption: "",
      options: ["The Dark Side Of The Moon", "Animals", "Atom Heart Mother", "The Piper at the Gates of Dawn", "The Wall", "Wish You Were Here",
       "A Momentary Lapse of Reason", "Meddle", "The Division Bell", "The Final Cut"]
    };
  },
  methods: {
    submitForm() {
      // Submit the form data here
    }
  }
};




</script>

<style>
* {
    margin: 0;
    border: 0;

}

div{
    display: inline-block;
}

img{
    justify-content: center;
    position: relative;
    margin-left: 1rem;
    margin-top: 3rem;
}



.covers{
    position: relative;
    height: 300px;
    width: 300px;
    margin-left: 3rem;
    margin-top: 3rem;
    transition: .5s ease;
}

.text{
   height: 115%;
    width: 115%;
    position: absolute;
    color: white;
    opacity: 0;
    top: 75%;
    left: 10%;
    text-align: center;
}



.covers:hover .text {
    visibility: visible;
    opacity: 1;
    backdrop-filter: blur(5px);
  }

  #money {
    position: fixed;
    min-width: 100%; 
    min-height: 100%;
  }
  form {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 500px;
  margin: 0 auto;
  padding: 20px;
}

label {
  font-weight: bold;
}

input[type="text"],
input[type="number"],
input[type="email"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  border: 1px solid black;
}

button {
  padding: 10px 20px;
  background-color: blue;
  color: white;
  border: none;
  border-radius: 5px;
  position: absolute;
}

</style>
