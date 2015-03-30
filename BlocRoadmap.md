### Questions

#### High-level
- Why the Morph / View Split?
- Why split event fetcher and handlers?
- I get moving the event handling logic out of hand, but why not route it back through the hand? Since the hand represents a user, it seems nice and logical that it should symbolically emit the events, even if it delegates the actual work

#### Class-related
- BlSpaceMorph: Why does it know about the clipboard?

### Understanding
BlUniverse - manages BlSpaces

BlSpace
  - uniquely named
  - [hack]: has a manager for Morphic compatibility, which should eventually be removed
  - has a root morph

BlBlocSpace
  - loop manager - handles the UI process
  - event fetcher
  - event handler

BlSpaceMorph
  - Like a Morphic world, but presents layers, from back to front - world, 

### Experiments

#### Create a Bloc Space to play with (not "the official" way)

```
space := BlBlocSpace new.
canvas := FormCanvas extent: Display extent depth: Display depth.
space rootMorph fullDrawOn: canvas.
canvas
```