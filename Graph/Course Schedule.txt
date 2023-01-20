class Solution {
public:
    
    bool dfs(int i,vector<int>&v,vector<int>&v1,vector<int>adj[]){
        v[i]=1;
        v1[i]=1;
        for(auto it:adj[i]){
            if(!v[it]){
                if(dfs(it,v,v1,adj))return true;
            }else if(v1[it])return true;
        }
        v1[i]=0;
        return false;
    }

    bool canFinish(int numCourses, vector<vector<int>>& prerequisites) {
        int n=numCourses;
        vector<int>adj[n];
        for(auto it:prerequisites){
            adj[it[0]].push_back(it[1]);
        }
        vector<int>v(n,0),v1(n,0);

        for(int i=0;i<n;i++){
            if(!v[i]){
                if(dfs(i,v,v1,adj))return false;
            }
        }
        return true;
    }
};