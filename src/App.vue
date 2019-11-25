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
      
    hindiToHunterianConsonentsMap:{
      'ka':'0915',
      'kha':'0916',
      'ga':'0917',
      'gha':'0918',
      'nga':'',
      'cha':'091A',
      'chha':'091B',
      'ja':'091C',
      'jha':'091D',
      'na':'091E',
      'ta':'091F',
      'tha':'0920',
      'da':'0921',
      'dha':'0922',
      'na':'0923',
      'ta':'0924',
      'tha':'0925',
      'da':'0926',
      'dha':'0927',
      'na':'0928',
      'pa':'092A',
      'pha':'092B',
      'ba':'092C',
      'bha':'092D',
      'ma':'092E',
      'ya':'092F',
      'ra':'0930',
      'la':'0932',
      'wa':'0935',
      'sa':'0936',
      'sha':'0937',
      'ha':'0939',
    },
    hindiToHunterianVowelsMap:{
      'a':'',
      'aa':'',
      'i':'',
      'u':'',
      'e':'',
      'ai':'',
      'o':'',
      'au':'',
      'ri':'',
      'a':'',
      'a':'',
      'a':'',
      'a':'',
      'a':'',
      'a':'',
    },
    hindiToHunterianConjunctsMap:{
      'ksha':'',
      'tra':'',
      'gya':'',
      'shra':'',
    }

    }
  }
  
}
</script>

<style>


</style>
