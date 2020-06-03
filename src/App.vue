<style>
  body {
    margin: 0;
    padding: 0;
    height: 100vh;
    overflow: hidden
  }
  * {
    box-sizing: border-box
  }
  ::-webkit-scrollbar {
    display: none;
  }
  :any-link {
    text-decoration: none;
    color: inherit
  }
  #app {
    font-family: 'Roboto', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    background-color: #fff;
    display: grid;
    place-items: center;
    justify-items: center;
    height: 100vh;
    color: #212121
  }
  #phone {
    background-image: url('assets/img/iphone.png');
    background-size: cover;
    height: fit-content;
    width: fit-content;
  }
  #phone--screen {
    width: 375px;
    height: 812px;
    margin: 1.75rem;
    background-size: cover;
    border-radius: 2.5rem;
    display: grid;
    justify-items: center;
    overflow-y: auto;
    user-select: none;
    cursor: grab;
    grid-template-rows: 28px 1fr;
    background-color: skyblue;
    position: relative
  }
  #phone--screen * {
    z-index: 1
  }
  #phone--notch {
    width: 57.5%;
    border-radius: 0 0 2.5rem 2.5rem;
    background-color: #111;
    height: 1.7rem;
    position: sticky;
    top: 0;
    z-index: 99;
  }
  #exercises--container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: .75rem;
    padding: .75rem;
    width: 100%;
    height: fit-content;
    align-self: end;
    background-color: white
  }
  .exercise {
    border-radius: .25rem;
    background-color: red;
    color: white;
    padding: .75rem;
    height: calc(103.66px * 1.66);
    display: grid;
    grid-gap: .5rem;
    place-items: center;
    grid-template-rows: 40% auto auto auto
  }
  .exercise:last-of-type {
    grid-template-rows: auto auto;
    grid-gap: 1rem
  }
  .exercise:last-of-type span, .exercise:last-of-type p {
    display: none;
  }
  .exercise:last-of-type svg {
    align-self: end
  }
  .exercise:last-of-type h2 {
    align-self: start
  }
  .exercise * {
    margin: 0
  }
  .exercise h2 {
    font-size: 1rem
  }
  .exercise .value {
    font-size: 1.5rem
  }
  .exercise p {
    margin-top: -.5rem;
    color: #ffffffaa;
    font-size: .9rem
  }
  .exercise svg {
    font-size: 2rem
  }
  .illustration {
    height: 100%;
    width: 100%
  }
  iframe {
    position: absolute;
    left: 0;
    right: 0;
    top: -50px;
    bottom: 0;
    height: 100%;
    width: 100%;
    z-index: 0;
  }
</style>

<template>
  <div id="app">
    <div id="phone">
      <div id="phone--screen">
        <div id="phone--notch" />
        <iframe width="600" height="450" frameborder="0" style="border:0" src="https://www.google.com/maps/embed/v1/view?zoom=13&center=-33.8900%2C151.2093&key=AIzaSyB_eUy-TLumn-xrcgDcWHk7zxrTsTEsaOg" allowfullscreen></iframe>
        <div id="exercises--container">
          <div v-for="exercise in exercises" :key="exercise.title" class="exercise" :style="{backgroundColor: exercise.color}">
            <font-awesome-icon :icon="exercise.icon"/>
            <h2>{{exercise.title}}</h2>
            <span class="value">{{exercise.value}}</span>
            <p class="exercise--distance">{{exercise.unit}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        exercises: [
          { title: 'Walking', value: 2, unit: 'Kilometres', icon: 'hiking', color: '#E9A655' },
          { title: 'Running', value: 4, unit: 'Kilometres', icon: 'running', color: '#659980' },
          { title: 'Skiing', value: 11, unit: 'Kilometres', icon: 'skiing', color: '#77777D' },
          { title: 'Cycling', value: 5, unit: 'Kilometres', icon: 'biking', color: '#002447' },
          { title: 'Swimming', value: 9, unit: 'Kilometres', icon: 'swimmer', color: '#69409e' },
          { title: 'More', icon: 'plus', color: '#e63946' }
        ]
      }
    }
  }
</script>
