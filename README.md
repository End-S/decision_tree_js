# decision_tree_js
Implementation in JavaScript of Josh Gorden's (@random-forests) decision tree classifier tutorial.

This is a complete JavaScript re-write of [this](https://github.com/random-forests/tutorials/blob/master/decision_tree.py) basic CART decision tree algorithm originally written in Python
by @random-forests for a Google Developers YouTube [series](https://youtu.be/LDRbO9a6XPU).

## Example usage
```javascript
const DecisionTree = require('./decision-tree');

const trainingData = [
  { colour: 'Green', diameter: 3, fruit: 'Apple'},
  { colour: 'Yellow', diameter: 3, fruit: 'Apple'},
  { colour: 'Red', diameter: 1, fruit: 'Grape'},
  { colour: 'Red', diameter: 1, fruit: 'Grape'},
  { colour: 'Yellow', diameter: 3, fruit: 'Lemon'},
]

// fruit is the property name associated with the classificaiton or label
// colour and diameter are the features
const model = new DecisionTree('fruit', ['colour', 'diameter'], trainingData);

console.log('Generated decision tree:')
// prints the generated tree
model.printTree()

// make a new prediction
console.log('\nPrediction for {colour: \'Red\', diameter: 2}:')
console.log(model.classify({colour: 'Red', diameter: 2}))
```

The above example can be run from the project root with:
`node example.js`
