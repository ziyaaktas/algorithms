# Two pointers

This method is especially handy when there is a need for keeping track of more than one variable or value in an algorithm.

**Example problems:**   
- Given an array of integers `numbers` that is already _**sorted in ascending order**_, find two numbers such that they add up to a specific `target` number.  
- Given an array `nums` of _n_ integers, are there elements _a_, _b_, _c_ in `nums` such that _a_ + _b_ + _c_ = 0? Find all unique triplets in the array which gives the sum of zero.

The idea is similar to the "Sliding Window" algorithm where we are following x amount of pointers & moving them as needed.  Two pointers array problems usually require the array to be sorted, especially for an array of numbers.

Let's have a look at the first problem.

Here we have a target number we are trying to reach by adding up two members of the given array.  We have to somehow iterate through the given array & figure it out.  Since the array is sorted already, two pointers method works well: One of our pointers start from the beginning & the other from the end.  As we are adding the two pointers, if we exceed our target value we decrement our end pointer index or vice versa, if we are below our target value we increment our start pointer.

