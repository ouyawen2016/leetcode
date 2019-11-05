```java
class Solution {
    public int removeDuplicates(int[] nums) {
        //双指针，前指针标记新数组，后指针遍历数组并找出不重复元素
        int pre = 0;
        int end = 0;
       while(end<nums.length){
            if(nums[end]==nums[pre]){//遍历到重复
                end++;
            }
            else{//不重复,移动到下一位
                pre++;
                nums[pre]=nums[end];
                end++;
            }
        }
        return pre+1;//题目要求返回数字，经过测试要求返回的是新数组长度
    }
}
```



