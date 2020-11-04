# 前序遍历
* BinaryTree


```
public class Main {
	public static void main(String[] args) {
		binaryTree binarytree=new binaryTree();
		Number no1=new Number(1);
		Number no2=new Number(3);
		Number no3=new Number(5);
		Number no4=new Number(6);
		Number no5=new Number(8);
		Number no6=new Number(9);
		binarytree.setRoot(no3);
		no3.setLeft(no2);
		no3.setRight(no5);
		no2.setLeft(no1);
		no5.setLeft(no4);
		no5.setRight(no6);
		binarytree.preOrder();
	}
}
class Number{
	private int no;
	private Number left;
	private Number right;
	
	public Number(int no) {
		this.no=no;
	}
	
	public int getNo() {
		return no;
	}

	public void setNo(int no) {
		this.no = no;
	}
	
	public Number getLeft() {
		return left;
	}

	public void setLeft(Number left) {
		this.left = left;
	}

	public Number getRight() {
		return right;
	}

	public void setRight(Number right) {
		this.right = right;
	}

	@Override
	public String toString() {
		return "Number [no=" + no + "]";
	}
	
	
	public void preOrder() {
		System.out.println(this);
		if(this.left!=null) {
			this.left.preOrder();
		}
		if(this.right!=null) {
			this.right.preOrder();
		}
	}	
}
class  binaryTree{
	private Number root;
	public void setRoot(Number root1) {
		this.root=root1;
	}
	public void preOrder() {
		if(this.root!=null) {
			this.root.preOrder();
		}else {
			System.out.println("空");
		}
	}
}
```

