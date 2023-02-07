# Leetcode-problems
Arrays

//Two sum

class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] arr= new int[2];
        for(int i =0; i<(nums.length-1) ; i++){
            for(int j=i+1; i<nums.length; j++){
                if( nums[i] + nums[j] == target){
                    arr[0]=i;
                    arr[1]=j;
                }
            }
        }
        return arr;
    }
}

//common prefix
class Solution {
    public String longestCommonPrefix(String[] strs) {
        if(strs.length==0) return "";
        String prefix=strs[0];
        for(int i=1;i<strs.length;i++){
            while(strs[i].indexOf(prefix)!=0){
                prefix=prefix.substring(0,prefix.length()-1);
                if(prefix.isEmpty()) return "";
            }
        }
        return prefix;
    }
}

// remove duplicate elements

class Solution {
    public int removeDuplicates(int[] nums) {
            int p = 0;
        for(int i = 1 ; i < nums.length ; i++){
            if(nums[p] != nums[i]){
                nums[p+1] = nums[i];
                p++;
            }
        }
        return p + 1;
        
    }
}

//remove element

class Solution {
    public int removeElement(int[] nums, int val) {
        int j=0;
        for(int i=0;i<nums.length;i++){
            if(val!=nums[i]){
                int temp=nums[j];
                nums[j]=nums[i];
                nums[i]=temp;
                j++;
            }
        }
        return j;
        
    }
}

search in search position

class Solution {
    public int searchInsert(int[] nums, int target) {
        int l=nums.length;
        for(int i=0;i<nums.length;i++){
            if(nums[i]==target) return i;
            else if(target<nums[i])  return i;
            
        }
        if(nums[l-1]<target) return l;
        return l;
    }
}


//plus one(66)
class Solution {
    public int[] plusOne(int[] digits) {
        int n=digits.length;
        for(int i=n-1;i>=0;i--){
            if(digits[i]<9){
                digits[i]++;
                return digits;
            }
            digits[i]=0;
        }
         int[] newnumber=new int[n+1];  // for case of{9},{99};{999}.....
        newnumber[0]=1;
        return newnumber;
    }
}
