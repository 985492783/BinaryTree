# Algorithms
# KMP
 * [Cyclic Nacklace](#Cyclic Nacklace)
# Cyclic Nacklace
```
import java.util.Scanner;

public class Main {
	static int[] next;
	public static void getNext(String p)
    {
        int k = -1;
        int j = 0 ;
        next[0] = -1;

        while (j < p.length())
        {
            if (k == -1 || p.charAt(k) == p.charAt(j))
            {
                k++;
                j++;
                next[j] = k;
            }else {
                k = next[k];
            }
        }
    }

	public static void main(String[] args) {
		
		Scanner in=new Scanner(System.in);
		while(in.hasNext()) {
			int k=in.nextInt();
			while(k-->0) {
			String str=in.next();
			next=new int[str.length()+1];
			getNext(str);
			int cycle=str.length()-next[str.length()];
			int length=str.length();
			int res=0;
			if((length!=cycle && length%cycle==0)|| length==1) {
				res=0;
			}else {
				res=cycle-length%cycle;
			}
			System.out.println(res);
			}
		}
	}

}

```
