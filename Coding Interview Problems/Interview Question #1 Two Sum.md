# Given an aray of integers, return the indices of the two numbers that add up to a given target.

*Understanding the question: You get an array of the random numbers, like [ 1, 3, 7, 9, 2 ], and a target (for example 11). Which two numbers from the array will sum up to 11? Return the indeces of those numbers. For this example its [3,4]*

## Steps to solve the problem:

**Step 1: Verify the constraints (Understand question better).**

###### Ask Interviever:
* Are all the numbers positive or can there be negatives?
* Are there duplicate numbers in the array?
* Will there always be a solution available / What do we return if there is no solution?
* Can there be multiple pairs that add up to the target?

**Step 2: Write out some test cases**

Array | Target | Return
------|---------|--------------
[1, 3, 7, 9, 2] | t=11 | [3, 4]
[1, 3, 7, 9, 2] | t=25 | null
[ ] | t=1 | null
[ 5 ] | t=5 | null
[1,6] | t=7 | [0, 1]

**Step 3: Figure out solution without code**

*Think about the solution that doesnt require code at first. How would you find two numbers from the array [1, 3, 7, 9, 2] that sum up to 11?*

**Step 4: Coding**

    const arr = [1, 3, 7, 9, 2];
    const target = 11;
    let i = 0;

    function foo() {

        for (n=1; n<arr.length; n++) {

            let P1 = arr[i];
            let P2 = arr[n];
            let NumToFind = P1+P2;

            if (NumToFind==target) {
                console.log("[" + P1 + "," + P2 + "]");
            }
        }

        i++
    }

    arr.forEach(foo);


