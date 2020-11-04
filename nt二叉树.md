# 二叉树
* BinaryTree
  * [二叉树的插入](#二叉树的插入)
    * [自动存贮](#自动存贮)
    * [手动插入](#手动插入)
  * [二叉树的遍历](#二叉树的遍历)
    * [preOrder](#preOrder)
    * [inOrder](#inOrder)
    * [postOrder](#postOrder)
    
    
    
# 二叉树的插入
定义一个类，给数据
```
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
	
}
```
二叉数的方法-定义根？
```
class  binaryTree{
	private Number root;
}
```
## 自动存贮
```
binaryTree binarytree=new binaryTree();
Scanner in=new Scanner(System.in);
while(true) {
	int n=in.nextInt();
	binarytree.add(new Number(n));
	binarytree.preOrder();
}
``` 
即大于this的数放right  
小于this的数放left  
直到this的下一位为空  
在Number类添加方法
```
class Number{
public void addNo(Number number) {
	if(number.no>this.no) {
		if(this.right==null) {
			this.right=number;
		}
		else {
			this.right.addNo(number);
		}
	}
	if(number.no<=this.no) {
		if(this.left==null) {
			this.left=number;
		}else {
			this.left.addNo(number);
		}
	}
}
}
```
在binarytree类中添加引用 
```
class binarytree{
public void add(Number number) {
	if(this.root==null) {
		this.root=number;
	}else {
		root.addNo(number);
	}
}
}
```
## 手动插入
听名字就知道很傻逼
# 二叉树的遍历
## preOrder
```
class binaryTree{
public void preOrder() {
	if(this.root!=null) {
		this.root.preOrder();
	}else {
		System.out.println("空");		}	
	}
}
```
分别在两个类中加入preOrder方法
遍历顺序：根-左-右
```
class Number{
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
```

## inOrder
```
class binaryTree{
public void inOrder() {
	if(this.root!=null) {
		this.root.preOrder();
	}else {
		System.out.println("空");		}	
	}
}
```
分别在两个类中加入inOrder方法
遍历顺序：左-根-右
```
class Number{
public void inOrder() {
	if(this.left!=null) {
		this.left.preOrder();
	}
	System.out.println(this);
	if(this.right!=null) {
		this.right.preOrder();
	}
}
}
```
## postOrder
```
class binaryTree{
public void postOrder() {
	if(this.root!=null) {
		this.root.preOrder();
	}else {
		System.out.println("空");		}	
	}
}
```
分别在两个类中加入postOrder方法
遍历顺序：左-右-根
```
class Number{
public void postOrder() {
	if(this.left!=null) {
		this.left.preOrder();
	}
	if(this.right!=null) {
		this.right.preOrder();
	}
	System.out.println(this);
}
}
```
