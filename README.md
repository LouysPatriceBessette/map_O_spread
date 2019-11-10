# map_O_spread
Deep copy function for ANY variable

The **map_O_spread** function is a super short "deep copy" function for ANY variable type.

## Why that name?
The idea comes from the copy of an array:
```
array.map(O=>{
  return [...el]
})
```
Notice the ```.map()``` method... The ```O``` argument... The *spread* operator.
Actually, **Map-O-Spread** is a a maple sugar brand: https://www.amazon.com/Spread-Pack-800g-6-49-shipping/dp/B00T2B9CD4
 heheh ;)
 
Now, the above is not a ***deep copy***, but a copy of the "1st level" of the variable.


## Why two functions? 
I wanted it to be recursive AND to work for ALL variable structure.
It worked well quite fast on nested arrays: https://repl.it/@Bes7weB/Map-o-Spread
But failed with an object... So imagine with a complex object like:
```
{
  a: [ 1,2,3 ],
  b: {
    c: [ "hello", "world"],
    d:  4,
    e: myfunction,
    f: null
    g: {
      [
        {h: 5, i: 6},
        {h: 7, i: 8}
      ]
    }
  }
}
```


## Why two functions?
Additionnally... It got more complicated when I noticed that the JS ```typeof()``` was returning ***object*** for both *object* AND *arrays*!
See here: https://repl.it/@Bes7weB/typeof-NOT-returning-the-correct-type

So I also made a ```getRealType()``` function to fix that problem *(I can't figure out why JS never fixed that* ***[1]*** *)*.
That's why there is two functions in this map_O_spread.js file.

And I left them as separate functions, since the getRealType() may also be useful alone.

### Notes:

***[1]*** Only tested in Chrome... I think it is a JS interpreter issue. It may not be an issue with other browsers.


### === LICENCE : MIT
Made on 2019-11-10 while attending a Concordia Bootcamp: https://concordiabootcamps.ca/

**You can use and modify it freely**, but I would appreciate you mention my Git link, if you use it as-is in your project.
Enjoy!


