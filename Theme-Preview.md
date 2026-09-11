---
modified: 2026-09-11T04:16:22-04:00
---
This is your new *vault*.

Make a note of something, [[create a link]], or try [the Importer](https://help.obsidian.md/Plugins/Importer)!

When you're ready, delete this note and make the vault your own.

hello ==this== *is* a #tag **example** 

#this-is-a-tag-that-is-long

test *test* **test** ***test***

0 1 2 3 4 5 6 7 8 9 

**0 1 2 3 4 5 6 7 8 9**

! " # $ % ^ ' ( ) * + , - . / 

< = > ? @

```
0 1 2 3 4 5 6 7 8 9 

! " # $ % ^ ' ( ) * + , - . / 

< = > ? @
```

# Heading 1 

## Heading 2 

### Heading 3 

#### Heading 4

##### Heading 5

###### Heading 6

# Code

```python
# leetcode 1004
class Solution(object):
    def longestOnes(self, A, K):
        """
        :type A: List[int]
        :type K: int
        :rtype: int
        """
        start_index = 0
        for end_index in range(0, len(A)):
            K -= 1-A[end_index]
            if K < 0:
                K += 1-A[start_index]
                start_index += 1
        return end_index-start_index+1
```

```ts
// leetcode 560 subarray sum equals k
// #Medium #Top_100_Liked_Questions #Array #Hash_Table #Prefix_Sum #Data_Structure_II_Day_5_Array
// #Big_O_Time_O(n)_Space_O(n) #2025_03_28_Time_14_ms_(87.34%)_Space_67.32_MB_(18.02%)

function subarraySum(nums: number[], k: number): number {
    let tempSum: number = 0
    let ret: number = 0
    const sumCount: Map<number, number> = new Map()
    sumCount.set(0, 1)
    for (const num of nums) {
        tempSum += num
        if (sumCount.has(tempSum - k)) {
            ret += sumCount.get(tempSum - k)!
        }
        if (sumCount.has(tempSum)) {
            sumCount.set(tempSum, sumCount.get(tempSum)! + 1)
        } else {
            sumCount.set(tempSum, 1)
        }
    }
    return ret
}

export { subarraySum }
```