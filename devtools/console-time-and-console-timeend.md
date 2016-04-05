# console.time and console.timeEnd

The `console.time` and `console.timeEnd` methods allow developers to time any
routine and get a duration in milliseconds.  Since JavaScript performance
is becoming increasingly important, it's good to know basic techniques for
benchmarking routines.  One of the most basic benchmarking tools is
`console.time` with `console.timeEnd`

`console.time` starts the time and `console.timeEnd` stops the timer and spits
out the duration:

```javascript

// start timer
console.time( "testSomething" );

// (do some testing of a forEach, for example)

// end timer, get the elapsed time
console.timeEnd( "testSomething" );

// 3782.303ms (or whatever time elapsed)

```

Passing a timer name as the first argument allows you to manage concurrent
timers.  The `console.timeEnd` call immediately spits out the elapsed time
in milliseconds.

There are more advanced techniques for performance testing and benchmarking
but `console.time` and `console.timeEnd` provide a quick manual method for
speed testing.
