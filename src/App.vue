<script>
</script>

<template>
  <div class="wrapper">
    <h1>Weather Tracker</h1>
    <p>Track your City Weather</p>
    <input type="text" placeholder="Input City">
    <button>Recieve Weather</button>
  </div>
</template>

<style>

.wrapper{
  width: 900px;
  height: 500px;
  border-radius: 50px;
  background-color: rgb(244, 250, 255);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  justify-content: center;
}
.wrapper input{
  background: transparent;
  border: 2px solid black;
  border-radius: 10px;
  color: white;
  font-size: 14px;
  padding: 5px;
  outline: none;
}

.wrapper h1{
  font-weight:bolder
}
.wrapper button{
  padding: 5px;
  background: rgb(2,0,36);
background: linear-gradient(22deg, rgba(2,0,36,1) 0%, rgba(200,255,123,1) 0%, rgba(111,231,255,1) 100%);
border: 2px solid black;
border-radius: 10px;
font-size: 16px;
color: rgb(39, 44, 44);
}
.wrapper button:hover{
  background: rgba(200,255,123,1);
}
.wrapper button:active{
  background: rgb(89, 145, 12);
}
</style>
