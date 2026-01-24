# DCIT 201 - Programming I: Methods Assessment

## ⚠️ ACADEMIC INTEGRITY WARNING

**This is an individual assessment. You must complete this work on your own.**

### Prohibited Actions:
- ❌ Using AI tools (ChatGPT, Claude, Copilot, etc.) to generate code
- ❌ Copying code from classmates or online sources
- ❌ Sharing your solutions with others
- ❌ Using code generation tools or AI assistants

### Consequences:
Students found violating academic integrity policies will receive **ZERO** for this assessment and may face additional disciplinary action according to university regulations.

**Your submission timestamp and code will be reviewed. Any suspicious patterns or AI-generated code signatures will be investigated.**

---

## Assessment Overview

**Total Marks:** 100 points  
**Time Allocation:** This assessment is designed to take approximately 4-6 hours  
**Submission Deadline:** [27th January 2026]

This practical assessment tests your understanding of:
- Method definition and invocation
- Parameter passing (pass-by-value)
- Method overloading
- Variable scope
- Method abstraction and stepwise refinement
- Code reusability and modularity

---

## Instructions

1. **Clone this repository** to your local machine
2. **Complete all four questions** in their respective Java files
3. **Test your code thoroughly** - include your own test cases
4. **Commit and push** your solutions before the deadline
5. **Do not modify** the test files or directory structure

---

## Question 1: Complex Statistical Calculator (25 marks)

### File: `StatisticalCalculator.java`

Create a comprehensive statistical calculator that demonstrates your understanding of method overloading and value-returning methods.

### Requirements:

Implement the following methods:

1. **calculateMean()** - Three overloaded versions:
   - `public static double calculateMean(int num1, int num2)`
   - `public static double calculateMean(int num1, int num2, int num3)`
   - `public static double calculateMean(int[] numbers)` - for an array of integers

2. **calculateVariance()** - Two overloaded versions:
   - `public static double calculateVariance(int num1, int num2, int num3)`
   - `public static double calculateVariance(int[] numbers)`
   
   Formula: Variance = Σ(xi - mean)² / n

3. **calculateStandardDeviation()** - Two overloaded versions:
   - `public static double calculateStandardDeviation(int num1, int num2, int num3)`
   - `public static double calculateStandardDeviation(int[] numbers)`
   
   Formula: Standard Deviation = √variance

4. **findRange()** - One version:
   - `public static int findRange(int[] numbers)`
   
   Range = maximum value - minimum value

### Critical Requirements:
- The variance and standard deviation methods MUST call the calculateMean() method internally (demonstrate method reuse)
- The standard deviation methods MUST call the calculateVariance() method internally
- Handle edge cases (empty arrays, single element, etc.)
- Use proper return types
- All methods must be static
- Include a main method that demonstrates ALL method overloads with meaningful test cases

### Marking Criteria:
- Correct implementation of all overloaded methods (10 marks)
- Proper method reuse (5 marks)
- Accurate mathematical calculations (5 marks)
- Edge case handling (3 marks)
- Comprehensive test cases in main (2 marks)

---

## Question 2: Parameter Passing Deep Dive (25 marks)

### File: `ParameterPassingDemo.java`

Create a program that demonstrates a deep understanding of Java's pass-by-value mechanism with complex scenarios.

### Requirements:

1. **modifyPrimitive()** method:
   ```java
   public static void modifyPrimitive(int value)
   ```
   - Attempts to modify the parameter by adding 100 to it
   - Prints the value inside the method

2. **swapValues()** method:
   ```java
   public static void swapValues(int a, int b)
   ```
   - Attempts to swap the values of two integers
   - Prints values inside the method after "swapping"

3. **multiplyByFactor()** method:
   ```java
   public static void multiplyByFactor(double original, int factor)
   ```
   - Multiplies the original by the factor
   - Modifies the original parameter inside the method
   - Prints the result inside the method

4. **simulateCompoundInterest()** method:
   ```java
   public static double simulateCompoundInterest(double principal, double rate, int years)
   ```
   - Calculates compound interest
   - Modifies the principal parameter inside the method during calculation
   - Returns the final amount
   - Formula: A = P(1 + r)^years

5. **demonstratePassByValue()** main method:
   - Creates variables for each test scenario
   - Calls each method with these variables
   - Prints the variable values BEFORE and AFTER each method call
   - Includes detailed comments explaining WHY the values remain unchanged (or changed)

### Critical Requirements:
- After EACH method demonstration, include print statements showing the original variable values
- Add detailed comments explaining Java's pass-by-value behavior
- Your main method should clearly demonstrate that primitive parameters are NOT modified
- Include a summary section in comments explaining what you learned about pass-by-value

### Marking Criteria:
- Correct method implementations (10 marks)
- Comprehensive demonstration in main (8 marks)
- Detailed explanatory comments (5 marks)
- Clear understanding of pass-by-value shown through output (2 marks)

---

## Question 3: Grade Management System (30 marks)

### File: `GradeManager.java`

Design a sophisticated grade management system using method abstraction and stepwise refinement principles.

### Requirements:

Implement a system with the following methods:

1. **calculateLetterGrade()** - Two overloaded versions:
   ```java
   public static char calculateLetterGrade(double score)
   public static char calculateLetterGrade(int score)
   ```
   Grading scale:
   - A: 90-100
   - B: 80-89
   - C: 70-79
   - D: 60-69
   - F: 0-59

2. **calculateGPA()** - Two overloaded versions:
   ```java
   public static double calculateGPA(char grade)
   public static double calculateGPA(double[] scores)
   ```
   GPA scale: A=4.0, B=3.0, C=2.0, D=1.0, F=0.0

3. **printDetailedReport()** - void method:
   ```java
   public static void printDetailedReport(String studentName, double[] scores, String[] courseNames)
   ```
   Should print:
   - Student name
   - Each course name with score, letter grade, and GPA contribution
   - Overall average score
   - Overall GPA
   - Academic standing (Excellent: GPA≥3.5, Good: GPA≥2.5, Satisfactory: GPA≥2.0, Probation: GPA<2.0)

4. **isPassingGrade()** method:
   ```java
   public static boolean isPassingGrade(double score)
   ```
   Returns true if score ≥ 60

5. **countPassingScores()** method:
   ```java
   public static int countPassingScores(double[] scores)
   ```
   Must use isPassingGrade() method internally

6. **findHighestScore()** and **findLowestScore()** methods:
   ```java
   public static double findHighestScore(double[] scores)
   public static double findLowestScore(double[] scores)
   ```

7. **calculateWeightedAverage()** method:
   ```java
   public static double calculateWeightedAverage(double[] scores, double[] weights)
   ```
   Calculates average where each score has a specific weight
   Note: weights should sum to 1.0

### Critical Requirements:
- Demonstrate method abstraction - each method should do ONE thing well
- Methods must call other methods where appropriate (e.g., printDetailedReport calls calculateLetterGrade and calculateGPA)
- Include proper scope management for all variables
- main method must demonstrate a complete scenario with at least 5 students and 4 courses each
- Handle invalid inputs gracefully (negative scores, mismatched array lengths, etc.)

### Marking Criteria:
- Correct implementation of all methods (15 marks)
- Proper method abstraction and reuse (8 marks)
- Valid scope management (3 marks)
- Comprehensive test scenario in main (2 marks)
- Error handling (2 marks)

---

## Question 4: Recursive Method Challenge with Call Stack Analysis (20 marks)

### File: `RecursiveAnalysis.java`

Demonstrate advanced understanding of method calls, call stacks, and recursion.

### Requirements:

1. **factorial()** method:
   ```java
   public static long factorial(int n)
   ```
   Calculates n! recursively
   Must include print statements showing the call stack depth

2. **fibonacci()** method:
   ```java
   public static int fibonacci(int n)
   ```
   Calculates the nth Fibonacci number recursively
   Must include print statements tracking each call

3. **power()** method:
   ```java
   public static double power(double base, int exponent)
   ```
   Calculates base^exponent recursively
   Must handle negative exponents

4. **sumDigits()** method:
   ```java
   public static int sumDigits(int n)
   ```
   Recursively calculates the sum of digits in a number
   Example: sumDigits(1234) returns 10

5. **isPalindrome()** method:
   ```java
   public static boolean isPalindrome(String str, int start, int end)
   ```
   Recursively checks if a string is a palindrome

6. **visualizeCallStack()** - helper method:
   ```java
   public static void visualizeCallStack(String methodName, int depth)
   ```
   Creates a visual representation of call stack depth
   Example output:
   ```
   |-- factorial(5)
   |---- factorial(4)
   |------ factorial(3)
   ```

### Critical Requirements:
- All recursive methods must have base cases clearly identified in comments
- Each recursive method must call visualizeCallStack() to show its position in the call stack
- Include detailed comments explaining:
  - What happens to the call stack when the method is called
  - When stack space is created and released
  - The order of execution (going down vs. coming back up)
- Your main method should include a section that runs each recursive method and explains the call stack behavior

### Marking Criteria:
- Correct recursive implementations (8 marks)
- Call stack visualization (5 marks)
- Clear understanding demonstrated through comments (5 marks)
- Comprehensive demonstration in main (2 marks)

---

## Submission Guidelines

### File Structure:
```
your-repo/
│
├── README.md (this file)
├── StatisticalCalculator.java
├── ParameterPassingDemo.java
├── GradeManager.java
└── RecursiveAnalysis.java
```

### Before Submitting:
- ✅ All files compile without errors
- ✅ All files run without runtime exceptions
- ✅ Code is properly formatted and indented
- ✅ All methods have appropriate comments
- ✅ Variable names are meaningful and follow camelCase convention
- ✅ No unused variables or methods
- ✅ Each file includes comprehensive test cases in main()

### Git Commands for Submission:
```bash
git add .
git commit -m "Complete methods assessment"
git push origin main
```

---

## Grading Rubric Summary

| Question | Topic | Marks |
|----------|-------|-------|
| Q1 | Method Overloading & Reuse | 25 |
| Q2 | Parameter Passing | 25 |
| Q3 | Grade Management System | 30 |
| Q4 | Recursion & Call Stack | 20 |
| **TOTAL** | | **100** |

---

## Tips for Success

1. **Start Early:** Don't wait until the last minute
2. **Test Frequently:** Run your code after implementing each method
3. **Read Carefully:** Make sure you understand what each question asks
4. **Comment Thoroughly:** Explain your logic, especially for complex parts
5. **Handle Edge Cases:** Think about what could go wrong
6. **Follow Naming Conventions:** Use meaningful variable and method names
7. **Review Your Notes:** Refer back to lecture slides and examples

---

## Common Mistakes to Avoid

- ❌ Forgetting to make methods `static`
- ❌ Not matching parameter types correctly in overloading
- ❌ Trying to use variables outside their scope
- ❌ Forgetting return statements in value-returning methods
- ❌ Not testing with various inputs
- ❌ Poor variable naming (x, y, z instead of meaningful names)
- ❌ Missing edge case handling

---

## Getting Help

If you encounter issues:
1. Re-read the lecture slides on Methods (Session 2A)
2. Review the method examples provided in class
3. Attend office hours (check course schedule)
4. Post SPECIFIC questions on the course forum (don't share code)

**Remember:** The goal is to learn. If you're struggling, that's normal - but you must do the work yourself to truly understand.

---

## Declaration

By submitting this assessment, I declare that:
- This work is entirely my own
- I have not used AI tools to generate any code
- I have not copied from any other source
- I understand the consequences of academic dishonesty

**Good luck! Show what you've learned about methods! 🚀**
