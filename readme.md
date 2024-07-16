# JavaScript Practice Questions and Answers


### Question:
Create an array of objects, each representing a person with properties like name, age, and gender. Write a function to filter out all females and then map the remaining people to an array of names. Print the final result.

### Answer:
```javascript
// Array of people objects
const people = [
  { name: 'Alice', age: 25, gender: 'female' },
  { name: 'Bob', age: 30, gender: 'male' },
  { name: 'Charlie', age: 35, gender: 'male' },
  { name: 'Diana', age: 40, gender: 'female' }
];

// Function to filter out females and map to names
const filterAndMap = (people) => {
  const filteredPeople = people.filter(person => person.gender !== 'female');
  const namesArray = filteredPeople.map(person => person.name);
  return namesArray;
};

// Print the final result
console.log(filterAndMap(people)); // Output: [ 'Bob', 'Charlie' ]
```



### Question:
Create an array of objects representing books with properties like title, author, and year. Write a function that takes the array and returns a new array with only the book titles. Print the result.


### Answer :
```javascript

// Array of book objects
const books = [
  { title: 'Book1', author: 'Author1', year: 2000 },
  { title: 'Book2', author: 'Author2', year: 2010 },
  { title: 'Book3', author: 'Author3', year: 2020 }
];

// Function to extract titles
const extractBookTitles = (books) => {
  return books.map(book => book.title);
};

// Print the result
console.log(extractBookTitles(books)); // Output: ['Book1', 'Book2', 'Book3']
```

### Question
Write three functions: one to square a number, one to double a number, and one to add 5 to a number. Compose these functions to create a new function that squares a number, doubles the result, and then adds 5.


### Answer :
```javascript

// Functions for operations
const square = (x) => x * x;
const double = (x) => x * 2;
const add5 = (x) => x + 5;

// Composed function
const squareDoubleAndAdd5 = (x) => add5(double(square(x)));

// Example usage
console.log(squareDoubleAndAdd5(3)); // Output: 23 (3^2 = 9, 9 * 2 = 18, 18 + 5 = 23)
```
### Question

Write a function that searches an array of objects for a specific person by name. If found, modify their age property. Print the updated array.


### Answer :
```javascript
// Array of person objects
let persons = [
  { name: 'Alice', age: 25 },
  { name: 'Bob', age: 30 },
  { name: 'Charlie', age: 35 }
];

// Function to find and modify age
const findAndModifyAge = (persons, name, newAge) => {
  let found = false;
  const updatedPersons = persons.map(person => {
    if (person.name === name) {
      found = true;
      return { ...person, age: newAge };
    }
    return person;
  });

  if (!found) {
    console.log(`Person with name '${name}' not found.`);
  }

  return updatedPersons;
};

// Modify age of 'Bob' to 32
persons = findAndModifyAge(persons, 'Bob', 32);

// Print the updated array
console.log(persons);
// Output:
// [
//   { name: 'Alice', age: 25 },
//   { name: 'Bob', age: 32 },
//   { name: 'Charlie', age: 35 }
// ]
```



