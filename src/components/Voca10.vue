<template>
  <h1>{{ msg }}</h1>
  <button @click="loadImage">count is: {{ count }}</button>
  <p>10 words</p>
  <img :src="imagePath" style="width:100%" @click="onClickImage"/>
<p>{{ word }}</p>1

</template>

<script>
export default {
  name: 'Voca10',
  props: {
    msg: String
  },
  data() {
    return {
      count: 0,
      words: [  {word: "apple",   imagePath: [  "https://cdn.pixabay.com/photo/2016/10/09/23/02/apple-1727320_1280.jpg"
                                              , "https://c.pxhere.com/photos/65/74/apple_fruit_healthy-1214744.jpg!d"]}
               ,{word: "balloon", imagePath: [  "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Balloon_arch.jpg/800px-Balloon_arch.jpg?20060830053006"
                                              , "https://freesvg.org/img/luftballons.png"]} 
               ,{word: "birthday",imagePath: [  "https://upload.wikimedia.org/wikipedia/commons/thumb/3/34/Happy_Birthday_Wikipedia.JPG/800px-Happy_Birthday_Wikipedia.JPG?20120116204958"
                                              , "https://publicdomainvectors.org/photos/jean_victor_balin_gateau.png"]}
             ],
      index1: Math.floor( Math.random() * 3 ),
      index2: Math.floor( Math.random() * 2 ), 
    }
  },
  computed: {

    word(){
      let randomWord = this.words[this.index1].word;
      return randomWord;
    },

    imagePath(){
      let imagePath = this.words[this.index1].imagePath[this.index2];
      return imagePath;
    }

  },
  methods: {
     onClickImage() {
      //play the sound(pronunciation)
      this.count++
    },

    loadImage(){
      this.count++; 
            
      this.index1 = Math.floor( Math.random() * 3 );
      this.index2 = Math.floor( Math.random() * 2 );
    }
  }
}
</script>
