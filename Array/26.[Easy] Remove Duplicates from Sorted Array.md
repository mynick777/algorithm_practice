* algorithms
* Easy (35.96%)
* Total Accepted:    311.8K
* Total Submissions: 867.1K
* Testcase Example:  '[1,1,2]'


Given a sorted array, remove the duplicates in-place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.


Example:

Given nums = [1,1,2],

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively.
It doesn't matter what you leave beyond the new length.

## STL
```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if(nums.size() == 0)
            return 0;
            
        auto last = std::unique(nums.begin(), nums.end());
        return std::distance(nums.begin(), last);
    }
};
```

## Double index
```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        size_t size = nums.size();
        if(size == 0) return 0;

        int index = 1;
        for(int i=1; i<size; i++) {
            if(nums[index-1] != nums[i]) {
                nums[index] = nums[i];
                index++;
            }
        }

        return index;
    }
};
```
