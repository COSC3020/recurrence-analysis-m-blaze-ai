# Recurrence Analysis -- Mystery Function

Analyze the running time of the following recursive procedure as a function of
$n$ and find a tight big $O$ bound on the runtime for the function. You may
assume that each operation takes unit time. You do not need to provide a formal
proof, but you should show your work: at a minimum, show the recurrence relation
you derive for the runtime of the code, and then how you solved the recurrence
relation.

```javascript
function mystery(n) {
    if(n <= 1)
        return;
    else {
        mystery(n / 3);
        var count = 0;
        mystery(n / 3);
        for(var i = 0; i < n*n; i++) {
            for(var j = 0; j < n; j++) {
                for(var k = 0; k < n*n; k++) {
                    count = count + 1;
                }
            }
        }
        mystery(n / 3);
    }
}
```

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.


Amount of work (outside recursion):
(n^2)*(n)*(n^2) = n^5, 
resulting in $\Theta$(n^5) time.

Recurrence:
T(n) = 3*(T(n/3))+$\Theta$(n^5)                                

a = 3                                   Using (T(n) = a*T(n/b)+$\Theta$(n^d))
b = 3
d = 5

log_b(a) = log_3(3) = 1

d > log_b(a) = 5 > 1 = true; Case 1
mystery(n) run time is T(n) = $\Theta$(n^5).

As a result, the time grows proportionally to n^5 as n gets bigger.




“I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.”



