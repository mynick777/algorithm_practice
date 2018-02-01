* algorithms
* Medium (36.64%)
* Total Accepted:    140.4K
* Total Submissions: 383.1K
* Testcase Example:  '[]'


Follow up for "Remove Duplicates":
What if duplicates are allowed at most twice?


For example,
Given sorted array nums = [1,1,1,2,2,3],


Your function should return length = 5, with the first five elements of nums being 1, 1, 2, 2 and 3. It doesn't matter what you leave beyond the new length.

## Double index

```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        size_t size = nums.size();
        if(size <= 2) return size;

        int index = 2;
        for(int i=2; i< size; i++) {
            if(nums[i] != nums[index-2]) {
                nums[index] = nums[i];
                index++;
            }
        }

        return index;
    }
};
```
