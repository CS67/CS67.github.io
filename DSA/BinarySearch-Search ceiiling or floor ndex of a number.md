# 原理

## 

ceilling: the smallest element which greater than target, or equal to target

floor: the biggest element which smaller than target, or equal to target

二分查找target.

查找到最后找不到target时:

如果这个元素比target小, 那么start往后移动, 这个start元素就是大于target的最小元素, end元素是小于target的最大元素.

如果这个元素比target大, 那么end往前移动, 此时end元素是小于target的最大元素, start元素就是大于target的最小元素



ceilling返回start

```java
class Solution {
  public int searchInsert(int[] nums, int target) {
    int start = 0;
    int end = nums.length-1;
    while(start<=end){
      int mid= start+(end-start)/2;
        if(nums[mid]==target){
          return mid;
        }else if (nums[mid]<target){
          start=mid+1;
        }else{
          end=mid-1;
        }
    }
    return start;
  }
}
```

floor返回end

```java
class Solution {
  public int searchInsert(int[] nums, int target) {
    int start = 0;
    int end = nums.length-1;
    while(start<=end){
      int mid= start+(end-start)/2;
        if(nums[mid]==target){
          return mid;
        }else if (nums[mid]<target){
          start=mid+1;
        }else{
          end=mid-1;
        }
    }
    return end;
  }
}
```

