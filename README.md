# SingleLinkedList1
reverse printing of a Single Linked List
import java.util.*;
public class Slink
{
    class node{
        int data;
        node next;
        node(int data)
        {
            this.data=data;
            next=null;
        }
    }
    node head=null,temp=null;
    public void insert(int data){
        node newnode=new node(data);
        if(head==null)
        {
            head=newnode;
            temp=newnode;
        }
        else
        {
            temp.next=newnode;
            temp=newnode;
        }
    }
    void reverseprint(int n)
    {
        node temp1=head;
        node temp2=head;
        while(temp1.next!=null)
            temp1=temp1.next;
        int d=temp1.data;
        System.out.println(d);
        for(int i=0;i<n-1;i++)
        {
            while(temp2.next.data!=d)
                temp2=temp2.next;
            d=temp2.data;
            System.out.println(d);
            temp2=head;
        }
    }
    public static void main(String[] args)
	{
	    Scanner sc=new Scanner(System.in);
	    Slink X=new Slink();
	    int t=sc.nextInt();
	    int n=0,data=0;
	    for(int i=0;i<t;i++)
	    {
	        n=sc.nextInt();
	        for(int j=0;j<n;j++)
	        {
	           data=sc.nextInt();
	           X.insert(data);
	        }
	        X.reverseprint(n);
	    }
	}
}
