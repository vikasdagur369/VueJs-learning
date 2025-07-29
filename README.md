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

ref() :- it is used to create a reactive reference to value.
reactive me reactive objects bnate hai, multiple reference data type use kr skte hai, lekin ref() me single values use krte hai.
ref me primitive or reference dono use kr skte hai.

computed properties -> special kind of varible jo automatically update kr lete khudko jab yeh dependent data me change dekhte hai.

`
const firstName = ref("vikas")
const lastName = ref("dagur")

const fullName = computed(() => firstName.value + " " + lastName.value)
`

conditional rendering ->
v-if, v-if-else, v-else

v-show -> agar yeh true hai to vo element dikhega vrna nhi dikhega.

v-for diretive -> it is just like a for loop in javascript. to iterate over array or object.

keys -> virtual dom hota hai vuejs me, efficiently way se dom update krne k liye ke element identification jaruri hai, isliye keys jaruri hai. keys diye bina vue ko entire DOM structure recreate krna pdega.

<p v-for="(person,index) in array" :key="index"><p/>

props -> ways to transfer data from parent components to child components
<ChildComponent name="vikas dagur"/> -> this is how we tranfer data to child component. to get data in child component we have to import data using defineProps(['name_of_prop'])


slot -> space in a component, allow to create reusable components that can accept diff content while maintaining a consistent structure.

ek component bnao uske andr slot tag lgao, and ek aur parent component bnao jiske andr child component ke andr kuch bhi data pass krdo. 


Fallback content in slot refers to the default content that is displayed when no content is provided for a particular slot.
parent ne kuch nhi bheja hai, fir bhi slot ke andar kuch meaningfull rhe , yeh uske liye use hota hai.

named slot is a way to assign a specific name of a slot in a component.
 

Provide & inject function -> 
context api ki trh hai. 
1. import provide function from vue js
2. import child component 
 syntax :- 

 provide("employeeName",'vikas')
 provide("age",20)

 to get data in child component we have to use inject function. 

1. import inject from vuejs

const var_name = inject("prop_name")

watchers -> automatically update the dom when underlying data changes. allows us to reactively watch for changes in a specific property or expression. 

syntax -> watch(source,callback,options)

source -> ref(), reactive object, array, getter function

callback -> the callback function is called whenever some data changes.

options -> immediate , deep, flush, onTrack 

Template refs -> is a way to create a reference to a child component, element, or a DOM element within a template. this allows us to access and manipulate the referenced object directly in your components logic.

refs are commonly used to interact with child components, triggers imperative actions, or access properties and methods of DOM elements.

