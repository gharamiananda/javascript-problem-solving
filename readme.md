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

### Question

Create an array of numbers. Write a function that uses the reduce method to calculate the sum of all even numbers in the array.


### Answer :
```javascript
// Array of numbers
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// Function to calculate sum of even numbers using reduce
const sumOfEvenNumbers = (numbers) => {
  return numbers.reduce((sum, num) => {
    if (num % 2 === 0) {
      return sum + num;
    }
    return sum;
  }, 0);
};

// Print the result
console.log(sumOfEvenNumbers(numbers)); // Output: 30 (2 + 4 + 6 + 8 + 10 = 30)
```


### Question


Write a function that determines whether a given year is a leap year.

### Answer :
```javascript

// Function to check if a year is a leap year
const isLeapYear = (year) => {
  // Leap year condition: divisible by 4 and not divisible by 100, unless divisible by 400
  return (year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0);
};

// Example usage
const year = 2024;
if (isLeapYear(year)) {
  console.log(`${year} is a leap year.`);
} else {
  console.log(`${year} is not a leap year.`);
}
// Output: 2024 is a leap year.
```
### Question

Create an array of numbers with some duplicate values. Write a function to filter out the duplicate values and return a new array with only unique numbers. Print the result.


### Answer :
```javascript
// Array with duplicate numbers
const numbersWithDuplicates = [1, 2, 2, 3, 4, 4, 5, 6, 6, 7];

// Function to filter out duplicate numbers
const filterUniqueNumbers = (numbers) => {
  return [...new Set(numbers)];
};

// Print the result
console.log(filterUniqueNumbers(numbersWithDuplicates)); // Output: [1, 2, 3, 4, 5, 6, 7]

```

### Question



Write a function that takes an array of numbers and returns the maximum value.
### Answer :
```javascript


// Function to find maximum value in an array
const findMaxValue = (numbers) => {
  return Math.max(...numbers);
};

// Example usage
const numbers = [5, 2, 9, 1, 7];
console.log(findMaxValue(numbers)); // Output: 9



```


### Question



Create an array of objects representing students with 'name' and 'grades' properties. Write a function to sort the students by average grade in descending order.
### Answer :
```javascript


// Array of student objects
const students = [
  { name: 'Alice', grades: [85, 90, 88] },
  { name: 'Bob', grades: [95, 92, 88] },
  { name: 'Charlie', grades: [90, 85, 92] }
];

// Function to sort students by average grade in descending order
const sortStudentsByAverageGrade = (students) => {
  return students.sort((student1, student2) => {
    const avg1 = student1.grades.reduce((sum, grade) => sum + grade, 0) / student1.grades.length;
    const avg2 = student2.grades.reduce((sum, grade) => sum + grade, 0) / student2.grades.length;
    return avg2 - avg1; // Sort descending
  });
};

// Print the sorted array
console.log(sortStudentsByAverageGrade(students));
// Output:
// [
//   { name: 'Bob', grades: [95, 92, 88] },
//   { name: 'Charlie', grades: [90, 85, 92] },
//   { name: 'Alice', grades: [85, 90, 88] }
// ]



```