<template>
 <div class="container">
  <div class="form-group">
    <label for="text-area"> Textarea</label>
    <textarea class="form-control" id="text-area" rows="3" v-model="input"></textarea>
  </div>

  <div class="form-group">
    <label for="text-area-translated"> Translated Textarea</label>
    <textarea class="form-control" id="text-area-translated" rows="3" v-model="output"></textarea>
  </div>
 </div>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
    
    input:"pragati",
    previousletter:"",
    previousLetterConsonentOrVowel:"",   // 1 for vowel, 0 for consonent
    englishToHindiMapVowels:{
        'i':'इ',
        'ii':'ई',
        'a':'अ',
        'aa':'आ',
        'u':'उ',
        'uu':'ऊ',
        'e':'ए',
        'ai':'ऐ',
        'o':'ओ',
        'au':'औ',
    },
    englishToHindiMap:{

      'k':'क',
      'kh':'ख',
      'g':'ग',
      'gh':'घ',
      'ch':'च',
      'chh':'छ',
      'j':'ज',
      'jh':'झ',
      't':'त',
      'th':'थ',
      'T':'ट',
      'Th':'ठ',
      'd':'द',
      'D':'ड',
      'Dh':'ढ',
      'dh':'ध',
      'n':'न',
      'Ng':'ङ',
      'N':'ण',
      'Y':'य',
      'Yn':'ञ',
      'p':'प',
      'ph':'फ',
      'b':'ब',
      'bh':'भ',
      'm':'म',
      'y':'य',
      'r':'र',
      'rr':'र्‍',
      'l':'ल',
      'v':'व',
      'sh':'श',
      's':'स',
      'shh':'ष',
      'h':'ह',
      'c':'क',
      'f':'फ',
      'q':'क',
      'w':'व',
      'x':'ज',
      'z':'ज',
      'O':'ॐ',
    },
    englishToHindiMaatraMap:{ 
      'a':'ा',
      'i':'ि',
      'ii':'ी',
      'u':'ु',
      'uu':'ू',
      'e':'े',
      'ai':'ै',
      'o':'ो',
      'au':'ौ'
    },
    output:"",


    }
  },
  methods: {
     iteratreAndConvert() {

       for(let i =0;i<this.input.length;)
       {
          
          i = this.generateSubstring(i);
          console.log("After all i= "+i);


       }

    },
    isVowel(letter)
    {
        if(letter === 'a'||letter ==='o'||letter ==='e'||letter ==='i'||letter ==='u')
        {
          return 1;
        }
        else{
          return 0;
        }
    },
    generateSubstring(i){
      let substr = this.input[i];

      if(this.isVowel(substr)){
          // check if next character is also vowel
          console.log("this is vovel"+substr);

          if(this.isVowel(this.input[i+1])){
              console.log("Next is also vovel"+this.input[i+1]);
              substr+=this.input[i+1];
              i+=2;
          }
          /* Now Vowel is two letter word
             Check if some previous consonent is there
          */
          if(this.previousletter=="")
          {
              console.log("Previous letter empty");
              this.previousletter+=this.englishToHindiMapVowels[substr];
          }
          else
          {
              console.log("Previous letter present"+this.previousletter);
              this.previousletter+=this.englishToHindiMaatraMap[substr];
              console.log("After update"+this.previousletter);
          }
          this.output+=this.previousletter;
          console.log("Finally updated output"+this.output);
          i+=1;
          return i;

      }else{
          console.log("Consonet");
          let tempsubstr="";
          for(let x=i;x<Math.min(i+3,this.input.length);x++){
              tempsubstr+=this.input[x];
          }
          console.log("Tempstr="+tempsubstr);
          let validConsonet = this.returnValidConsonent(tempsubstr);
          console.log("Consonet returnd Object");
          console.log(validConsonet);
          if(validConsonet['length']==3)
          {
              i+=3;
          }
          else if(validConsonet['length']==2)
          {
              i+=2;
          }
          else if(validConsonet['length']==1)
          {
              i+=1;
          }
          this.previousletter = validConsonet['validConsonent'];
          if(i==this.input.length)
          {
              this.output+=this.previousletter;
          }
          console.log("finally previos letter in consonent"+this.previousletter);
          return i;
      }
    },
    returnValidConsonent(substr)
    {
        console.log("Substr to match "+substr);
      if(this.englishToHindiMap[substr])
      {
          console.log("Consonent of length "+substr.length);
          return {
              "validConsonent":this.englishToHindiMap[substr],
              "length":substr.length,
          }
      }
      else if(this.englishToHindiMap[substr.substring(0,substr.length-1)]){
          console.log("Consonent of length "+substr.length);
            return {
                "validConsonent":this.englishToHindiMap[substr.substring(0,substr.length-1)],
                "length":substr.length-1,
            }
      }
      else if(this.englishToHindiMap[substr.substring(0,substr.length-2)]){
          console.log("Consonent of length "+substr.length);
              return {
                  "validConsonent":this.englishToHindiMap[substr.substring(0,substr.length-2)],
                  "length":substr.length-2,
              }
      }
      else{
          console.log("something unexpected happened");
      }

    }
  },
  mounted() {
    this.iteratreAndConvert();
  }
  
}
</script>

<style>


</style>
