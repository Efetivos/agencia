# Efetivos Comunicação Visual:

> Descrição

<p>
Aqui você deixa de contratar uma empresa que presta serviços, para contratar uma Parceira que vai em busca das soluções com você. Nosso foco é entender o que você precisa e trazer o resultado desejado, seja ele: Vender mais, ter mais visibilidade ou aumentar o número dos seus clientes.
Ser EFETIVO é fazer AGORA e fazer correto.
Conte com a gente!<br><br></p>

> Principais links:
<ul>
    <li>Efetivos.com.br | (http://efetivos.com.br)</li>
</ul>






For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

> IMPORTAR LIBS EXTERNAS WEBPACK / VUE

#Libs:
``` bash
 GSAP: npm install --save-dev gsap
 Jquery: npm install --save-dev jquery
 ScrollMagic: npm install --save-dev scrollmagic
 (Verificar se todos constam no  Package.json)
 ```

 # gsap.animation(ScrollMagic)
 >Install imports-loader:
 > npm install --save-dev imports-loader (Verificar Package.json)
 > Incluir no arquivo "webpack.base.conf.js
 ``` bash
 resolve: { 
  ....
  alias: { //Seção Alias
  > "ScrollMagicGSAP": "scrollmagic/scrollmagic/uncompressed/plugins/animation.gsap"
  }
},

... //Seção Rules
module: {
  rules: [
    ....
    {
    > test: /\.js$/,
    > loader: "imports-loader?define=>false"
    },
  ],
},
....
 ```

# IMPORTAR/INSERIR DENTRO DO COMPONENTE.VUE > Dentro da tag <script>
 ``` bash
(import { TweenMax, TimelineMax } from 'gsap')
import $ from 'jquery'
import ScrollMagic from 'scrollmagic'
import 'ScrollMagicGSAP'
 ```

# Fazer animações dentro da função:
> export default { mounted(){ ......  }}
 ``` bash
export default { 
    mounted () { 

        //Animação vai aqui

    } //Close Mounted
} //Close Export Defautl

 ```

# TRANSIÇÃO COM ROTAS
> #usar o <router-link> no lugar da tag <a>
 ``` bash
<router-link to="/path"> Home </router-link> 
```

> #dentro da tag export default { .... } //Não de esquecer colocar onComplete:next depois da Timeline ou TweenMax
 ``` bash
beforeRouteLeave(to, from, next) {
    var tlTrans = new TimelineMax({onComplete:next}).fromTo(this.$refs.cross, 2 ,{width: 0}, {width:"100%", ease: Power3.easeIn})
  }
  ```