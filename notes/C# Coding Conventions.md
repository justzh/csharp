# C# Coding Conventions

Coding conventions serve the following purposes:
    
- They create a consisten look to the code, so that readers can focus on content, not layout.
- They enable readers to understand the code more quickly by making assumptions bsaed on previous experience.
- They facilitate copying, changing, and maintaining the code.
- They demonstrate C# best practices.


## Naming Conventions

Example:

    var currentPerformanceCounterCategory = new System.Diagnostics.
        PerformanceCounterCategory();


## Layout Conventions

Good layout uses formatting to emphasize the structure of your code and to make the code easier to read. Microsoft examples and samples conform to the following conventions:
    
- Use the default Code Editor settings.
- Write only one statement per line.
- Write only one declaration per line.
- If continuation lines are not indented automatically, indent them one tab stop (for spaces).
- Add at least one blank line between method definitions and property definitions.
- Use parentheses to make clauses in an expression apparent, as shown in the following code.
    
    ```
    if ((val1 > val2) && (val1 > val3))
    {
        // Take appropriate action.
    }
    ```

## Commenting Conventions

- Place the comment on a separate line, not at the end of a line of code
- Begin comment text with an uppercase letter.
- End comment text with a period.
- Insert one space between the comment delimiter (//) and the comment text.
- Do not create formatted blocks of asterisks around comments

## Language Guidelines

The following sections describe practices that the C# team follows to prepare code examples and samples.

### String Data Type

- Use string interpolation to concatenate short strings, as shown in the following code.
string displayName = $"{nameList[n].LastName}, {nameList[n].FirstName}";
- To append strings in loops, especially when you are working with large amounts of text, use a StringBuilder object.

    ```
    var phrase = "lalalalalalalalalalalalalalalalalalalalalalalalalalalalalala";
    var manyPhrases = new StringBuilder();
    for (var i = 0; i < 10000; i++)
    {
        manyPhrases.Append(phrase);
    }
    // Console.WriteLine("tra" + manyPhrases);
    ```
    
### Implicitly Typed Local Variables

- Use implicit typing for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.
    
    ```
    var var1 = "This is clearly a string.";
    var var2 = 27;
    ```
    
- Do not use var when the type is not apparent from the right side of the assignment
   
    ```
    // When the type of a variable is not clear from the context, use an
    // explicit type. You generally don't assume the type clear from a method name.
    // A variable type is considered clear if it's a new operator or an explicit cast.
    int var3 = Convert.ToInt32(Console.ReadLine());
    int var4 = ExampleClass.ResultSoFar();
    ```

- Do not rely on the variable name to specift the type of the variable. It might not be correct.

- Avoid the use of `var` in place of dynamic.

- Use implicit typing to determine the type of the loop variable in for loops.

    ```
    var phrase = "lalalalalalalalalalalalalalalalalalalalalalalalalalalalalala";
    var manyPhrases = new StringBuilder();
    for (var i = 0; i < 10000; ++i)
    {
        manyPhrases.Append(phrase);
    }
    Console.WriteLine("tra" + manyPhrases);
    ```

- Do not use implicit typing to determine the type of the loop variable in `foreach` loops.

    ```
    foreach (char ch in laugh)
    {
        if (ch == 'h')
            Console.Write("H");
        else
            Console.Write(ch);
    }
    Console.WriteLine();
