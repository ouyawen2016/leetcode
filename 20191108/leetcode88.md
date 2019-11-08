```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        //双指针标记法,分别标记最后一位
        int p = m - 1;
        int q = n - 1;
        int cur = m + n-1;
        while(q>=0&&p>=0){//比较大小，将较大的一位复制到新数组末尾
            if(nums1[p]>nums2[q]){
                nums1[cur]=nums1[p];
                cur--;
                p--;
            }else{
                 nums1[cur]=nums2[q];
                cur--;
                q--;
            }
           
        }
        while(q>=0){//若此时数组二仍然有剩余，复制到新数组中
            nums1[cur]=nums2[q];
            cur--;
            q--;
        }
         
    }
}
```

