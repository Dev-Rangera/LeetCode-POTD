# LeetCode-POTD
Problem of The Day 


Given two 0-indexed integer arrays nums1 and nums2, return a list answer of size 2 where:

answer[0] is a list of all distinct integers in nums1 which are not present in nums2.
answer[1] is a list of all distinct integers in nums2 which are not present in nums1.
Note that the integers in the lists may be returned in any order.



class Solution {
public:
    vector<vector<int>> findDifference(vector<int>& nums1, vector<int>& nums2) {
        unordered_set<int> set1(nums1.begin(), nums1.end());
        unordered_set<int> set2(nums2.begin(), nums2.end());
        vector<int> diff1, diff2;
        for (int num : set1) {
            if (set2.find(num) == set2.end()) {
                diff1.push_back(num);
            }
        }
        for (int num : set2) {
            if (set1.find(num) == set1.end()) {
                diff2.push_back(num);
            }
        }
        return {diff1, diff2};
    }
};
