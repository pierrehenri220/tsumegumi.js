# autokern.js
Simple font kerning via JavaScript.
The original work is a typography experiment from ![Takayuki Fukatsu](http://fladdict.net/exp/autokerning/)
This tiny javascript aims toto extend the original possibilities.

##How it works
The javascript parse dom text node and wrap them in a span tag (which is 'slow' by the way) adjusting *letter-spacing* or *margin* styles following the given rules.  
A random class is also created so you can add random styles too.

## How to use
```
new autokern({
    node:        [] // array or single native DOM element node
  , kerningInfo: [] // array of character: spacing (em). Default set is japanese
  , min:         -5 // Currenly Min / Max are used to generate randomly a classname
  , max:         5  // By default a range like this .r{min},...,r-1,r0,r1,...,r{max}
})
````

There is no wrapper for jQuery-like libraries.
You can just loop through the jquery selectors like this for example:
```
var mykern = new autokern();
$( '#long, .multiple, node' ).each(function() {
    mykern.update( this );
});
```