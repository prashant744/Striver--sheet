class Solution {
public:
    int search(vector<int>& nums, int target) {
        int i=0,j=nums.size()-1;
        while(i<=j){
            if(nums[i]==target)return i;
            else if(nums[j]==target)return j;
            i++;
            j--;
        }
        return -1;



        // for(int i=0;i<nums.size();i++){
        //     if(nums[i]==target){
        //         return i;
        //     }
        // }
        // return -1;
    }
};