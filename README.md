# my-project8-tic-tac-toe1
Based on Tic-Tac-Toe React tutorials in React Documentation.
This simple Vue.js project uses Tailwind CSS for styling and coloring components using inline CSS by using the style attribute in HTML elements.


Example:
```
<div class="text-purple text-sm absolute pin-b pin-r pt-4 px-4">Tailwind CSS test:Purple colored text from tailwind CSS</div>
```
LINK:https://codepen.io/krishnakurtakoti/full/BejQJR



                <template>
                  <div id="app">

                         <div class="font-bold text-purple">TIC TAC TOE GAME</div>

                        <div class="font-semibold text-orange-dark">This player's term:{{player}}</div>

                      <div class="board px-4 py-4">
                        <div> <button  class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark" v-on:click="buttonclick1(history3[0].id)"> {{history3[0].square}}</button>
                          <button class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark" v-    on:click="buttonclick1(history3[1].id)"> {{history3[1].square}}</button>
                          <button class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark" v-   on:click="buttonclick1(history3[2].id)"> {{this.history3[2].square}}</button>
                        </div>

                        <div> <button class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark"    v-on:click="buttonclick1(history3[3].id)"> {{history3[3].square}}</button>
                          <button class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark" v-   on:click="buttonclick1(history3[4].id)"> {{history3[4].square}}</button>
                          <button class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark" v-   on:click="buttonclick1(history3[5].id)"> {{history3[5].square}}</button>
                        </div>

                        <div> <button class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark"    v-on:click="buttonclick1(history3[6].id)"> {{history3[6].square}}</button>
                          <button class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark" v-   on:click="buttonclick1(history3[7].id)"> {{history3[7].square}}</button>
                          <button class="bg-transparent hover:bg-blue-dark text-black font-bold py-4 px-4 border border-grey-dark" v-    on:click="buttonclick1(history3[8].id)"> {{history3[8].square}}</button>
                        </div>
                      </div>



                        <div class="font-bold text-brown px-4 border boder-black py-2">Latest box clicked:{{latest}}</div>
                        <div class="font-bold text-orange px-4 border boder-black py-2">Move count:{{stepNumber3}}</div>
                        <div class="font-bold text-green px-4 border boder-black py-2">Win Status:{{winner}} </div>

                        <div class="text-blue-dark bg-yellow-light font-bold px-4 border boder-black py-2" v-if="(winner)">
                        Player {{history3[this.latest - 1].square}} is the winner! Game finished in {{stepNumber3}} moves</div>





                        <div class="text-purple text-sm absolute pin-b pin-r pt-4 px-4">Tailwind CSS test:Purple colored text from tailwind CSS</div>
                  </div>
                </template>

                <script>
                import HelloWorld from './components/HelloWorld.vue'
                import './assets/css/main.css'
                export default {
                  name: 'app',data(){
                    return{
                 history3:[{square:null ,id:1},{square:null,id:2},{square:null,id:3},{square:null,id:4},{square:null,id:5},{square:null,id:6},{square:null,id:7},{square:null,id:8},{square:null,id:9}],
                      stepNumber3:0,
                      latest:'',
                      isNextX3:true,
                      winner:false,
                      player:'X'
                    };
                  },methods:{
                       buttonclick1:function(i){

                       const isPlayer = ((this.stepNumber3 % 2) === 0) ? '0' :'X';

                       this.player = isPlayer;

                       const hist3=this.history3.slice(0,this.stepNumber3 + 1);

                      if((this.history3[i-1].square === 'X') ||(this.history3[i-1].square === '0') || this.winner){
                          return;
                          }
                      this.history3[i-1].square = this.isNextX3 ? 'X':'0' ;
                      this.stepNumber3 = hist3.length;
                      this.latest = i;
                      this.isNextX3 = !this.isNextX3;
                      const lines = [
                      [0, 1, 2],
                      [3, 4, 5],
                      [6, 7, 8],
                      [0, 3, 6],
                      [1, 4, 7],
                      [2, 5, 8],
                      [0, 4, 8],
                      [2, 4, 6],
                      ];

                        for (var i1 = 0; i1 < lines.length; i1++) {
                           const [a, b, c] = lines[i1];
                         if (this.history3[a].square && this.history3[a].square === this.history3[b].square && this.history3[a].square === this.history3[c].square) {
                             this.winner = true;
                            }
                         }
                      }
                    },
                  components: {
                    HelloWorld
                  }
                }
                </script>

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
