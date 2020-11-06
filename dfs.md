# Algorithms
* [全排列](#全排列)
## 全排列
```
import java.util.Scanner;

public class Main{
	static int n;
	static int[] arr;
	static int[] brr;
	static void dfs(int step) {
		if (step==n) {
			for(int i=0;i<n;i++) {
				System.out.print(arr[i]);
			}
			System.out.println();
		}else if(step<n) {
			for(int i=1;i<=n;i++) {
				if(brr[i]==0) {
					brr[i]=1;
					arr[step]=i;
					dfs(step+1);
					brr[i]=0;
				}
			}
		}else {
			return;
		}
	}
	public static void main(String[] args) {
		Scanner in=new Scanner(System.in);
		while(in.hasNext()) {
			n=in.nextInt();
			arr=new int[n+1];
			brr=new int[n+1];
			dfs(0);
		}
	}
	
}
```
