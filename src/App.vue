<template>
 <div class="container">
  <div class="form-group">
    <label for="text-area"> Textarea</label>
    <textarea class="form-control" id="text-area" rows="3"></textarea>
  </div>

  <div class="form-group">
    <label for="text-area-translated"> Translated Textarea</label>
    <textarea class="form-control" id="text-area-translated" rows="3"></textarea>
  </div>
 </div>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
    
    englishToHindiMap:{
      'a':'अ',
      'aa':'आ',
      'i':'इ',
      'ii':'ई',
      'u':'उ',
      'uu':'ऊ',
      'e':'ए',
      'ai':'ऐ',
      'o':'ओ',
      'au':'औ',
      'k':'क्',
      'ka':'क',
      'kh':'ख्',
      'kha':'ख',
      'g':'ग्',
      'ga':'ग',
      'gh':'घ्',
      'gha':'घ',
      'ch':'च्',
      'cha':'च',
      'chh':'छ्',
      'chha':'छ',
      'j':'ज्',
      'ja':'ज',
      'jh':'झ्',
      'jha':'झ',
      't':'त्',
      'ta':'त',
      'tha':'थ',
      'th':'थ्',
      'T':'ट्',
      'Ta':'ट',
      'Th':'ठ्',
      'Tha':'ठ',
      'd':'द्',
      'da':'द',
      'D':'ड्',
      'Da':'ड',
      'Dh':'ढ्',
      'Dha':'ढ',
      'dh':'ध्',
      'dha':'ध',
      'n':'न्',
      'na':'न',
      'Ng':'ङ्',
      'Nga':'ङ',
      'N':'ण्',
      'Na':'ण',
      'Yn':'ञ्',
      'Y':'य्',
      'Ya':'य',
      'Yna':'ञ',
      'p':'प्',
      'pa':'प',
      'ph':'फ्',
      'pha':'फ',
      'b':'ब्',
      'ba':'ब',
      'bh':'भ्',
      'bha':'भ',
      'm':'म्',
      'ma':'म',
      'y':'य्',
      'ya':'य',
      'r':'र्',
      'ra':'र',
      'rr':'र्‍',
      'l':'ल्',
      'la':'ल',
      'v':'व्',
      'va':'व',
      'sh':'श्',
      'sha':'श',
      's':'स्',
      'sa':'स',
      'shh':'ष्',
      'shha':'ष',
      'h':'ह्',
      'ha':'ह',
      'c':'क्',
      'ca':'क',
      'f':'फ्',
      'fa':'फ',
      'q':'क्',
      'qa':'क',
      'w':'व्',
      'wa':'व',
      'x':'ज्',
      'xa':'ज',
      'z':'ज्',
      'za':'ज',
      'O':'ॐ',
    },
    englishToHindiMaatraMap:{ 
      'aa':'ा',
      'i':'ि',
      'ii':'ी',
      'u':'ु',
      'uu':'ू',
      'e':'े',
      'ai':'ै',
      'o':'ो',
      'au':'ौ'
    },


    }
  }
  
}
</script>

<style>


</style>
