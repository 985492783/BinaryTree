# 动态规划
* [背包问题](#背包问题)
  * [01背包](#01背包)
  * [完全背包](#完全背包)
  
#背包问题  

#01背包 
最典型的采药
总时间T,总个数N
所花时间time[],所得价值value[]
```
int[][] dp=new int[N+1][T+1];
for(int i=1;i<=N;i++){
  for(int j=1;j<=V;j++){
    if(time[i]<=j){'
      dp[i][j]=Math.max(dp[i-1][j],dp[i-1][j-time[i]]+value[i]);
    }else{
      dp[i][j]=dp[i-1][j];
    }
  }
}
```
#完全背包  
