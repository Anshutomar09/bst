# bst

/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    TreeNode* f(vector<int> nums, int l, int h)
    {
        if(l>h)
            return NULL;
        int m = (l+h)/2;
        TreeNode* t=new TreeNode(nums[m]);
        t->left=f(nums, l, m-1);
        t->right=f(nums, m+1, h);
        return t;
    }
    TreeNode* sortedArrayToBST(vector<int>& nums) {
        return f(nums, 0, nums.size()-1);
    }
};
