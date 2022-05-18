class Solution:
    def pivotIndex(self, nums: List[int]) -> int:
        n=len(nums)
        pf=[0]*n
        pf[0]=nums[0]
        for i in range(1,n):
            pf[i]=pf[i-1]+nums[i]
        for i in range(n):
            if i==0:
                lsum=0
            else:
                lsum=pf[i-1]
            rsum=pf[n-1]-pf[i]
            if lsum==rsum:
                return i
        return -1
