<template>
  <div class="hello">
    <select v-model="selected" @change="onChange">
      <option value="birthday" selected>Happy Birthday</option>
      <option value="codes">Codes block</option>
      <option value="emoji">Some emoji</option>
    </select>
    <div id="editor">
      <textarea v-model="input" ></textarea>
      <vue-markdown :source="input" ></vue-markdown>
    </div>
  </div>
</template>

<script>
    import Vue from 'vue'
    import VueMarkdown from 'vue-markdown'

    Vue.component('vue-markdown',VueMarkdown);

export default {
  name: 'Markdown',
  data() {
      return {
          selected:1,
          input: '## Hello guys try me, you can also edit me in textarea ',
          birthday: '# Hey \n ' +
          '## Happy birthday Mike \n ' +
          'I wish you \n ' +
          '- money \n' +
          '- happiness \n' +
          ' - ~~die~~ \n ' +
          '- health \n ' +
          '_This is VladosMark_  (R)' ,
          codes:'``` javascript\n' +
          'var foo = function (bar) {\n' +
          '  return bar++;\n' +
          '};\n' +
          '\n' +
          'console.log(foo(5));\n' +
          '```\n'+
          'maybe its work+\n'
          +' ### (no)',

          emoji:'> Classic markup: :wink: :cry: :laughing: :yum:\n' +
          '>\n' +
          '> Shortcuts (emoticons): :-) :-( 8-) ;)',

      }
  },
    computed: {
    },
    methods: {
        onChange() {
          switch(this.selected){
              case 'birthday':
                  this.input=this.birthday;
                  break;
              case 'codes':
                  this.input=this.codes;
                  break;
              case 'emoji':
                  this.input=this.emoji;
                  break;
          }
        },
    }
}
</script>

<style scoped>



ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

code {
    background: #d3d3d3;
    padding: 20px;
    text-align: left;
}

 textarea {
   width: 400px;
   margin: 10px;
 }

    #editor {
        display: flex;
    }

    select {
        width: 300px;
        padding: 10px;
        border-radius: 3px;
    }
</style>
