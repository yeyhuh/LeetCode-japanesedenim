# 1. Two Sum

## Java ##

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i=0; i<nums.length; i++) {
            for(int j=i+1; j<nums.length; j++) {
                if(nums[i] + nums[j] == target) {
                    return new int[] {i,j};
                }
            }
        }
        return new int[] {};
    }
}
```

### Explanation ###
1. The twoSum method takes two parameters: an integer array called nums and an integer target. It returns an integer array containing the indices of the two numbers that add up to the target.

2. The code uses a nested loop to iterate through all possible pairs of numbers in the nums array. The outer loop iterates over each element of the array.

3. Inside the outer loop, the inner loop starts from the next element (index i+1) and iterates through the remaining elements.

4. In each iteration of the inner loop, the code checks if the sum of nums[i] and nums[j] (where i and j are the indices of the current elements) is equal to the target value.

5. If the sum is equal to the target, it means we have found the two numbers that satisfy the problem's condition. In this case, the code creates a new integer array on the fly using the values i and j, and returns it as the result.

6. If no such pair is found after checking all possible combinations, the code reaches the end of the method. In this case, it returns an empty integer array, indicating that there is no solution.

## Python ##

```py
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i+1, len(nums)):
                if i != j and nums[i] + nums[j] == target:
                    return i, j
```

### Explanation ###
1. The code defines a class called Solution with a method named twoSum. The method takes two parameters: nums, which is a list of integers, and target, which is the target value we want to find pairs for. The method returns a list containing the indices of the two numbers that add up to the target.

2. The code uses nested loops to iterate through all possible pairs of numbers in the nums list. The outer loop iterates over the indices of the list.

3. Inside the outer loop, the inner loop starts from the next index (i+1) and iterates through the remaining indices of the list.

4. In each iteration of the inner loop, the code checks if the sum of nums[i] and nums[j] (where i and j are the indices of the current elements) is equal to the target value.

5. The code also includes a condition if i != j to ensure that the same element is not considered twice. This condition prevents selecting the same index for both numbers in the pair.

6. If the sum is equal to the target and the indices i and j are different, it means we have found a valid pair that satisfies the problem's condition. In this case, the code returns a list containing the values of i and j.

7. If no such pair is found after checking all possible combinations, the code continues to the next iteration until all pairs have been checked. If no solution is found, the method implicitly returns None.

or

```py
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hMap = {}   # val : ind

        for i, n in enumerate(nums):
            difference = target - n
            if difference in hMap:
                return hMap[difference], i
            hMap[n] = i
```

### Explanation ###
1. The code defines a class called Solution with a method named twoSum. The method takes two parameters: nums, which is a list of integers, and target, which is the target value we want to find pairs for. The method returns a list containing the indices of the two numbers that add up to the target.

2. The code initializes an empty dictionary called hMap. This dictionary will be used to store the numbers in the nums list as keys and their corresponding indices as values.

3. The code uses a for loop combined with the enumerate function to iterate over the nums list. The enumerate function provides both the index (i) and the value (n) of each element in the list.

4. Inside the loop, the code calculates the difference by subtracting the current element (n) from the target value. The difference represents the number we need to find in order to form a pair that adds up to the target.

5. The code checks if the difference exists as a key in the hMap dictionary using the in operator. If it does, it means we have found a pair that satisfies the problem's condition. In this case, the code returns a list containing the value stored in hMap[difference] (which is the index of the difference number) and the current index (i).

6. If the difference is not found in the hMap dictionary, it means we haven't encountered its corresponding number yet. In this case, the code adds the current element n to the hMap dictionary as a key and its index i as the corresponding value. This allows us to store the information needed for future lookups.

7. If no pair is found after iterating through all elements of the nums list, the code implicitly returns None.
