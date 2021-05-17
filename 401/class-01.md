# Reading Notes for Class 01

## Pain and Suffering

- Well, this was a great intro lol!

- The price of growth is pain. Physical, mental, emotional!

- Thats a lot of bullet points about being exhausted...

- I'm totally not intimidated

- All of these things however, help with growth. 

- This is not the same as Suffering

- Suffering is pain without purpose. As I learned in 301, the pain that came with learning wasn't suffering, it had a purpose.

### Consider the following

1. What's your perspective?
2. Why are you doing this?
3. Do you want what comes at the end of this journey
4. Are you doing this for you?

- I think these were great things to remember while going through this journey

## A beginner's guide to Big O Notation

- Big O notation is used in Computer Science to describe the performance or complexity of an alorithm.

- describes worst- case scenario and can be used to describe execution time required by an algorithm

### 0(l)

- describes an algorith that will always execute in the same time (or space) regardless of the size of the input data set.

-example

```py
bool IsFirstElementNull(IList<String> elements)
{
    return elements[0] == null;
}
```

### O(N)

- describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set (what)

```py
bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}
```

### O(N²) as in squared

- represents an algorithm whose performance is directly proportional to the square of the size of the input data set. Common for nested iterations over data set.

```py
bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}
O(2^N)
```

### O(2^N)

- growth doubles with each addition to the input data set. The growth curve function is exponential- starting off very shallow, then rising meteorically. Example is a recursive calculation of Fibonacci

```py 
int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}
```

### Logarithms

- used to search sorted data sets. 

- compares median of selected data and compares it against a target value.

- if match, it will return success
