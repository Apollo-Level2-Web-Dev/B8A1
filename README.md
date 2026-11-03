# B8A1

## Assignment: Problem Solving with TypeScript & OOP

This assignment assesses your practical understanding of core TypeScript concepts from Modules 1, 2, and 3—including basic types, optional/default/rest parameters, readonly tuples, interfaces, type narrowing, generics, Promises, and Object-Oriented Programming (OOP).

---

## Problem Solving (50 Marks)

All coding solutions must be implemented in a **single file** named `solutions.ts`.

---

## Problem 1:
Create a function `formatString` that accepts a string and an optional boolean parameter.

- If the boolean parameter is `true` or not provided, return the string in **uppercase**.
- If the boolean parameter is `false`, return the string in **lowercase**.

### Requirements:
- You must write the correct types for the function parameters and the return type.

```tsx
// Sample Input:
formatString("TypeScript");
formatString("TypeScript", true);
formatString("TypeScript", false);

// Sample Output:
"TYPESCRIPT"
"TYPESCRIPT"
"typescript"
```

---

## Problem 2:
Create a function `processInput` that accepts a value which may be a **string**, **number**, or **boolean**, and returns a formatted result based on the value's type:

- If the input is a **string** → return the length of the string multiplied by **2**.
- If the input is a **number** → return the number multiplied by **10**.
- If the input is a **boolean** → return `"Active"` if `true`, or `"Inactive"` if `false`.

### Requirements:
- You must write the correct union type for the function parameter and the return type.
- You must use type narrowing (`typeof`) to handle each case safely.

```tsx
// Sample Input:
processInput("hello");
processInput(7);
processInput(true);
processInput(false);

// Sample Output:
10
70
"Active"
"Inactive"
```

---

## Problem 3:
Create a function `formatCoordinate` that accepts a **readonly tuple** representing a coordinate and location name in the order of `[latitude, longitude, locationName]`, and returns a formatted location string.

### Requirements:
- Apply the `readonly` modifier to the tuple parameter so it cannot be modified inside the function.
- Return the exact string format shown in the sample output.

```tsx
// Sample Input:
formatCoordinate([23.81, 90.41, "Dhaka"]);
formatCoordinate([22.35, 91.78, "Chittagong"]);

// Sample Output:
"Location: Dhaka (23.81, 90.41)"
"Location: Chittagong (22.35, 91.78)"
```

---

## Problem 4:
Create a generic function `concatenateArrays` that accepts multiple arrays of the **same type** using rest parameters and returns a single combined array containing all elements in order.

### Requirements:
- Must use a generic type parameter and rest parameters.
- Do not use `any`.

```tsx
// Sample Input:
concatenateArrays(["a", "b"], ["c", "d"]);
concatenateArrays([1, 2], [3, 4], [5]);

// Sample Output:
["a", "b", "c", "d"]
[1, 2, 3, 4, 5]
```

---

## Problem 5:
Define an interface `Course` with the following properties:
- `title` (string)
- `students` (number)
- `isPublished` (boolean)

Then, create a function `getPopularCourses` that accepts an array of `Course` objects and a `minStudents` number. The function should return a **new array** containing only the courses that are currently published (`isPublished` is `true`) and have `students` greater than or equal to `minStudents`.

### Requirements:
- Define the `Course` interface properly.
- Do not mutate the original array.

```tsx
// Sample Input:
const courses = [
  { title: "TypeScript Mastery", students: 120, isPublished: true },
  { title: "Draft Course", students: 200, isPublished: false },
  { title: "Basic HTML", students: 45, isPublished: true },
  { title: "Next.js Pro", students: 85, isPublished: true }
];

getPopularCourses(courses, 80);

// Sample Output:
[
  { title: "TypeScript Mastery", students: 120, isPublished: true },
  { title: "Next.js Pro", students: 85, isPublished: true }
]
```

---

## Problem 6:
Write a generic function `getPropertyValues` that takes an array of objects and a property key as arguments, and returns a new array containing the values of that specific key from each object. Use generic constraints to ensure the key exists on the objects in the array.

### Requirements:
- Use generics with the `keyof` constraint.
- Do not use `any`.

```tsx
// Sample Input:
const users = [
  { id: 1, name: "Rakib", role: "Admin" },
  { id: 2, name: "Sadia", role: "Editor" },
  { id: 3, name: "Tariq", role: "Subscriber" }
];

getPropertyValues(users, "name");
getPropertyValues(users, "id");

// Sample Output:
["Rakib", "Sadia", "Tariq"]
[1, 2, 3]
```

---

## Problem 7:
Create an `Employee` class with a `protected` property `name` and a `private` property `baseSalary`. Add a method `getDetails` in `Employee` that returns `"Employee: [name], Base Salary: [baseSalary]"`.

Then, create a subclass `Manager` that extends `Employee` and adds a `private` property `department`. Include a method `getRoleInfo` in the `Manager` class that returns `"Manager of [department]: [name]"`.

### Requirements:
- Use a constructor and `super()` properly to initialize properties.
- Use `protected` and `private` access modifiers as specified.

```tsx
// Sample Input:
const manager = new Manager("Alice", 50000, "Engineering");
manager.getDetails();
manager.getRoleInfo();

// Sample Output:
"Employee: Alice, Base Salary: 50000"
"Manager of Engineering: Alice"
```

---

## Problem 8:
Create a function `calculateTotalPrice` that accepts an array of product objects. Each product object has the following properties:
- `name` (string)
- `price` (number)
- `quantity` (number)
- `discount` (optional number between 0 and 100, representing a percentage discount)

The function should return the **total price** of all products after applying each product's discount (if provided). If the array is empty, return `0`.

### Requirements:
- Write an interface or type alias for the product object.
- Properly handle the optional `discount` property.

```tsx
// Sample Input:
const products = [
  { name: "Pen", price: 10, quantity: 2 },
  { name: "Notebook", price: 25, quantity: 3, discount: 10 },
  { name: "Bag", price: 50, quantity: 1, discount: 20 }
];

calculateTotalPrice(products);

// Sample Output:
127.5
```

---

## Blog Task (10 Marks)

Write an impactful and technically detailed blog post on **any 2 of the following questions**:

1. What are the core differences between `type` aliases and `interface` in TypeScript? When should you choose one over the other?
2. How does TypeScript's type hierarchy work with `any`, `unknown`, and `never`? Why is `unknown` always preferred over `any`?
3. What is **Type Narrowing** in TypeScript? Provide practical examples using `typeof`, `instanceof`, and the `in` operator.
4. How do **Generics** work in TypeScript, and how do they help when working with asynchronous `Promise<T>` responses?
5. Explain how Access Modifiers (`public`, `private`, `protected`, and `readonly`) work in TypeScript OOP with examples.
6. What happens to TypeScript code under the hood during compilation (`tsc`), and what role does `tsconfig.json` play?
7. Provide a practical example of combining **Union (`|`)** and **Intersection (`&`)** types in TypeScript.

### Blog Rules & Instructions:

- **File Naming:** Submit each blog post in its own Markdown file named after the blog topic using the format `[blog-name].md` (e.g., `type-vs-interface.md`, `type-narrowing.md`).
- **Length Requirement:** Every blog post must have **at least 500 sentences**.
- **Structure:** Each blog must have a clear **Title**, **Introduction**, **Detailed Body Paragraphs with Code Examples**, and **Conclusion**.
- **Language:** English or Bangla.

---

## Coding Requirements

All coding solutions must be placed in a single file named `solutions.ts`.

- **Exact Function & Class Names:** You must use the exact function, interface, and class names specified in the problem descriptions (`formatString`, `processInput`, `formatCoordinate`, `concatenateArrays`, `Course`, `getPopularCourses`, `getPropertyValues`, `Employee`, `Manager`, `getDetails`, `getRoleInfo`, `calculateTotalPrice`).
- **Exact Output:** Your function and method return values must **exactly match** the sample outputs, including spaces, punctuation, and capitalization.
  - *Correct:* `"Employee: Alice, Base Salary: 50000"`
  - *Incorrect:* `"employee: Alice, base salary: 50000"`
- **Clean Code:** Use meaningful variable names and avoid using `any`.
- **No Noise:**
  - Do **not** include comments like `// Problem 1`, `// Problem 2`, etc., in `solutions.ts`.
  - Do **not** include any `console.log` statements in your final `solutions.ts` file; always `return` the values.
- **Originality:** All code and blog writing must be your own work. Plagiarism (copying from friends, documentation, or AI generators) will result in a **zero**.

---

## File Structure

```text
├── solutions.ts
├── [blog-name-1].md
├── [blog-name-2].md
└── README.md
```

---

## Submission Guidelines

1. **Repository Setup:** Create a personal GitHub repository and push your completed `solutions.ts`, `[blog-name].md` files, and `README.md`.
2. **Visibility:** Set the repository to **Public**.
3. **Submission:** Paste the **direct GitHub repository URL** into the assignment submission box. Do not submit individual files or zip archives.

---

## Assignment Schedule & Deadlines

- **Assignment Release:** November 07, 2026 – *8:00 PM*
- **60 Marks Deadline:** November 08, 2026 – *11:59 PM*
- **50 Marks Deadline:** November 09, 2026 – *11:59 PM*
- **30 Marks Deadline:** November 09, 2026 (*after 11:59 PM*) to November 30, 2026 – *before 11:59 PM (Next 21 Days)*
