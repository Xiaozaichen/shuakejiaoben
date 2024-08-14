# shuakejiaoben
https://www.16personalities.com/ch/结果/intp-a/x/crj8uf6vq
class Solution {
public:
    vector<int> leftmostBuildingQueries(vector<int>& heights, vector<vector<int>>& queries) {
        int n = heights.size();
        int q = queries.size();
        stack<int> st;
        vector<int> ans(n,-1);
        vector<int> jilu(n,-1);
        st.push(0);
        int i = st.top()+1;
        while(!st.empty() && i<n){
            while(!st.empty() && heights[st.top()] < heights[i]){
                jilu[st.top()] = i;
                st.pop();
            }
            st.push(i);
            i++;
        }
        for(int i = 0; i < q;i++){
            if(queries[i][0] == queries[i][1]){
                ans[i] = i;
                continue;
            }
            if(queries[i][0] > queries[i][1]){
                swap(queries[i][0],queries[i][1]);
            }
            if(heights[queries[i][0]] < heights[queries[i][1]]){
                ans[i] = queries[i][1];
                continue;
            }
            else{
                st.push(queries[i][0]);
                int j = queries[i][1] + 1;
                while(j < n && !st.empty()){
                    while(!st.empty() && heights[st.top()] < heights[j]){
                        
                    }
                }
            }
        }

    }
};
