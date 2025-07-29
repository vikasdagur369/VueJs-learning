vue js -> easy to learn, it is flexible, component based, popular, light weight.

1. npm create vue@latest
2. choose some or skip , then vue project will be build.

each component will have three sections :- 1. <script> 2. <template> 3.<style>

Text interpolation => allows us to display javascript expression or a varible within the markup or html.
 syntax is -> {{js expression}}

we cant declare variable inside {{}}, we have to declare variable inside script tag.

Attribute binding -> html elements ko attribute dene ke liye hume yha alag syntax use krna pdta hai -
```
 <a v-bind:href="any variable name">vikas dagur<a/>
```
or 
<a :href="myLink">hi hello<a/>

vue.js Reactivity -> it means framework can automatically uodate ui when the info behind it changes. it is similiar to useState() in react.
we have two functions : 1.reactive() 2. ref()

reactive() -> it is used to create reactive objects. reactive object ek esa object hai jo khudki properties me changes ko automatically detect kar leta hai, jisse ui me updates trigger hojate hai.
 bas Object par kaam krega ,primitive datatypes nhi use kr skte.

syntax :-
1. sbse pehle reactive ko import kro vue se.
2. fir ek varible me uska reference lelo, and rective function me object define krdo.
e.g - let intialState = reactive({count : 0})

ab ui par render krne template me likhenge, {{intialValue.count}}.

events lgane kisi bhi element par humko @ use krna pdega , jese agar kisi button pr click krne pr kya hota hai, yeh check krne humko @click use knra pdegaa.

