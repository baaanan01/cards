<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="wrapper">
      <div class="box1">
        <img
          class="img"
          alt="spike"
          src="https://i.pinimg.com/564x/a9/b5/b6/a9b5b624f317efc409c7054c675b957d.jpg"
          width="250"
        />
        <p>Spike Spiegel<br />Space Cowboy</p>
      </div>
      <div class="box1">
        <h3>Information</h3>
        <form>
          <label for="fname">First name:</label><br/>
          <input type="text" id="fname" name="fname" required /><br/>
          <label for="lname">Last name:</label><br />
          <input type="text" id="lname" name="lname" /><br/>
          <h4>important question</h4>
          <textarea class = "formmmm" placeholder = "your favourite beer..." name="message" rows="3" cols="20">
          </textarea><br/>
          <input class="rainbow rainbow-1" type="submit" value="Submit" />
          <input class="btn" type="reset" value="Reset"/>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  // mounted() {
  //   const SubmitBtn = document.querySelector("SubmitBtn");
  //   SubmitBtn.addEventListener("click", ($event) => {
  //     console.warn($event);
  //   });
  // },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Montserrat");
@import url("https://fonts.googleapis.com/css?family=Poppins");

/* CSS flexbox — модуль макета гибкого контейнера — представляет собой способ компоновки элементов, в основе лежит идея оси.
Flexbox состоит из гибкого контейнера (flex container) и гибких элементов (flex items). 
Гибкие элементы могут выстраиваться в строку или столбик, а оставшееся свободное пространство распределяется между ними различными способами.*/

.wrapper {
  max-width: 1170px;
  margin-left: auto;
  margin-right: auto;
  padding-left: 16px;
  padding-right: 16px;
  grid-template-columns: repeat(2, 1fr);
  display: flex;
  flex-wrap: wrap; /* flex-wrap задаёт правила вывода flex-элементов —  в одну строку или в несколько, с переносом блоков.  */
  justify-content: center; /*CSS свойство  justify-content определяет, как браузер распределяет пространство между и вокруг элементов контента
                               вдоль главной оси flex контейнера, или вдоль строчной оси grid контейнера. */
}

.box1 {
  margin-left: auto;
  margin-right: auto;
  padding-left: 16px;
  padding-right: 16px;
  grid-row: 1/2;
  border: 1px solid;
  flex: 1 1 100px;
  margin: 0 5px;
  background: #ffffff;
  box-shadow: 0 4px 38px rgba(0,0,0,0.25), 0 1px 1px rgba(0,0,0,0.22);
}


.img {
  margin-top: 10px;
}
.btn {
  font-family: Poppins, sans-serif;
  background-color: rgb(252, 186, 186);
  color: black;
  
  border-radius: 4px;
  padding: 8px 16px;
  border: 0;
  margin: 10px;
}
.btn:hover {
  /*Чтобы при наведении курсора блок увеличивался, мы воспользуемся свойством transform и зададим ему значение scale(1.2).
   При этом блок увеличится на 20 процентов с сохранением своих пропорций: */
  -webkit-transform: scale(1.2);
  -ms-transform: scale(1.2);
  transform: scale(1.3);
  /* при наведении на кнопку меняется цвет  */
  background-color: #b81010;
  color: rgb(255, 253, 253);
}

.container {
  margin-top: 150px;
}

.text-center {
  text-align: center;
}

.rainbow {
  font-family: Poppins, sans-serif;
  background-color: #343a40;
  color: rgb(255, 253, 253);
  cursor: pointer;
  border-radius: 4px;
  padding: 8px 16px;
  border: 0;
  margin: 10px;
}

.rainbow-1:hover {
  background-image: linear-gradient(
    90deg,
    #00c0ff 0%,
    #ffcf00 49%,
    #fc4f4f 80%,
    #00c0ff 100%
  );
  animation: slidebg 5s linear infinite;
}
@keyframes slidebg {
  to {
    background-position: 20vw;
  }
}

.follow {
  margin-top: 40px;
}

.follow input {
  color: black;
  padding: 8px 16px;
  text-decoration: none;
}

/* .box2 {
  margin-left: auto;
  margin-right: auto;
  padding-left: 16px;
  padding-right: 16px;   
  grid-row: 1 / 2;
  border: 1px solid;
  flex:  1 1 100px;
  margin: 0 5px
} */

/* перенос работает и без медиа если есть flex-wrap
 @media (max-width: 500px) {
  .grid>div:not(.head) {
    width: 100%;
  }
  .grid>div:not(.head):nth-child(odd) {
    order: 2;
  }
} 
:nth-child() находит один или более элементов,
основываясь на их позиции среди группы соседних элементов.
*/
</style>





<!--   <div class="row">
      <div class="column">
        <img
          alt="представим что тут картинка"
          src="src\components\богдан.jpg"
        />
        <div class="text-block">Богдан Кандауров<br /></div>
        <p class="paragraph">Молодой предприниматель</p>
      </div>

      <div class="column">
        <div class="form">
          <form>
            <label for="fname">First name:</label><br />
            <input
              class="form"
              type="text"
              id="fname"
              name="fname"
              required
            /><br />
            <label class="textform" for="lname">Last name:</label><br />
            <input class="form" type="text" id="lname" name="lname" required />
            
          </form>
        </div>
        <button class="btn1" type="submit">Submit</button>
          <button class="btn2" type="reset">Clear</button>
      </div>
    </div>

    <h4>BUTTON</h4>
    <button id="SubmitBtn" type="submit">Кнопка</button>
 .column {
  float: left;
  width: 50%;
}

.row:after {
  content: "";
  display: table;
  clear: both;
}
.row {
  display: flex;
}

.column {
  margin-left: 10%;
  margin-right: 10%;
  background: rgb(228, 255, 246);
  flex: 50%;
  
}
.text-block {
  margin-top: 10px;
  font-family: Montserrat, sans-serif;
  text-align: left;
}
.paragraph {
  text-align: left;
  margin-top: 10px;
  font-family: Montserrat, sans-serif;
}
.form {
  margin-left: 10px;
  text-align: left;
  margin-top: 5px;
}
.btn {
  margin-left: 10px;
  text-align: left;
  margin-top: 15px;
}
.textform {
  margin-top: 15px;
}
.btn1 {
  font-family: Poppins, sans-serif; 
  background-color: #64c568;
  border-color: #64c568;
  border-radius: 8px;
  margin-top: 15px;
  font-size: 16px;
  width: 100px;
  margin: 10px;
}
.btn1:hover {
  /* при наведении на кнопку меняется цвет 
  background-color: white;
  border-color: white;
  color: black;
} 
-->

