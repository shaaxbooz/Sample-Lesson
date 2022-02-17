<template>
<header>
  <div class="card">
      <div class="text">Quyidagilardan birini tanlang!</div>
  </div>

  <div class="question" :class="imgques?'enabled':''"
  :style="imgques? { display:flex }:{}">
    {{questionText?questionText:'Savol:'}}
    <img class="questionimage" :src="imgques">
  </div>

  <div class="random-boxs">
    <div class="container"> 
      <div class="random-box" @click="randomnumber(question.id)" v-for="question in questions" :class="question.selected && 'selected'">
        {{question.selected===false?question.id:question.rand}}
      </div>
    </div>
  </div>
</header>
</template>

<script>
import './theme.css'
import './main.css'
export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      questionText:'',
      imgques: '',
      randNumbers: [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27],
      randNumber: '',
      questions: [
        {
          id: 1,
          imgQuestion: './img/1.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 2,
          imgQuestion: './img/2.jpg',
          txtQuestion: "a ning qanday qiymatlarida tenglama 4ta ildizga ega bo'ladi ? ",
          selected: false,
          rand: ''
        },
        {
          id: 3,
          imgQuestion: './img/3.jpg',
          txtQuestion: "Tenglamaning ildizlarini yig'indisini toping:",
          selected: false,
          rand: ''
        },
        {
          id: 4,
          imgQuestion: './img/4.jpg',
          txtQuestion: 'Nechta tub son tenglikni qanoatlantiradi:',
          selected: false,
          rand: ''
        },
        {
          id: 5,
          imgQuestion: './img/5.jpg',
          txtQuestion: "Tenglamani ildizlari yig'indisini toping: ",
          selected: false,
          rand: ''
        },
        {
          id: 6,
          imgQuestion: './img/6.jpg',
          txtQuestion: 'Tenglama nechta ildizga ega? ',
          selected: false,
          rand: ''
        },
        {
          id: 7,
          imgQuestion: './img/7.jpg',
          txtQuestion: "Tenglama ildizlarini yig'indisini toping: ",
          selected: false,
          rand: ''
        },
        {
          id: 8,
          imgQuestion: './img/8.jpg',
          txtQuestion: 'Tenglama nechta ildizga ega? ',
          selected: false,
          rand: ''
        },
        {
          id: 9,
          imgQuestion: './img/9.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 10,
          imgQuestion: './img/10.jpg',
          txtQuestion: "Tenglamani ildizlar ko'paytmasini toping: ",
          selected: false,
          rand: ''
        },
        {
          id: 11,
          imgQuestion: './img/11.jpg',
          txtQuestion: 'Tengama a ning qanday qiymatlarida 4 ta ildizga ega boladi? ',
          selected: false,
          rand: ''
        },
        {
          id: 12,
          imgQuestion: './img/12.jpg',
          txtQuestion: 'Tengama a ning qanday qiymatlarida 2 ta ildizga ega boladi? ',
          selected: false,
          rand: ''
        },
        {
          id: 13,
          imgQuestion: './img/13.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 14,
          imgQuestion: './img/14.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },{
          id: 15,
          imgQuestion: './img/15.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 16,
          imgQuestion: './img/16.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 17,
          imgQuestion: './img/17.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 18,
          imgQuestion: './img/18.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 19,
          imgQuestion: './img/19.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 20,
          imgQuestion: './img/20.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 21,
          imgQuestion: './img/21.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 22,
          imgQuestion: './img/22.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 23,
          imgQuestion: './img/23.jpg',
          txtQuestion: 'Tenglamani yeching: ',
          selected: false,
          rand: ''
        },
        {
          id: 24,
          imgQuestion: './img/24.jpg',
          txtQuestion: "Tenglama ildizlarini yig'indisini toping: ",
          selected: false,
          rand: ''
        },
        {
          id: 25,
          imgQuestion: './img/25.jpg',
          txtQuestion: "Tenglama ildizlarini yig'indisini toping: ",
          selected: false,
          rand: ''
        },
        {
          id: 26,
          imgQuestion: './img/26.jpg',
          txtQuestion: "Tengama a ning qanday qiymatlarida ildizga ega bo'lmaydi? ",
          selected: false,
          rand: ''
        },
        {
          id: 27,
          imgQuestion: './img/27.jpg',
          txtQuestion: 'Tenglama nechta ildizga ega? ',
          selected: false,
          rand: ''
        }
      ]
    }
  },
  methods: {
    randomnumber(idx) {
      this.randNumber = Math.floor(Math.random()*this.questions.length);
      while (this.randNumbers[this.randNumber] === '') {
        this.randNumber = Math.floor(Math.random()*this.questions.length);
      }
      if(this.questions[idx-1].selected===false) {
        this.questions[idx-1].rand = this.randNumbers[this.randNumber];
        this.questions[idx-1].selected = true; 
        this.imgques = this.questions[this.questions[idx-1].rand-1].imgQuestion;
        this.questionText = this.questions[this.questions[idx-1].rand-1].txtQuestion;
      }
      this.randNumbers[this.randNumber] = '';
      
      console.log(this.questions[idx-1]);
    }
  }
}
</script>

<style>
</style>
