# delete-all-method-in-linked-list
import java.util.*;
import java.lang.*;
import java.io.*;

public class Main
{
	public static void main (String[] args) throws java.lang.Exception
	{
		Scanner sc=new  Scanner(System.in);
                int n=sc.nextInt();
                check p=new check();
                for(int i=0;i<n;i++){
                        p.add(sc.nextInt());
                }
               // p.addfirst(5);
                //p.deletefirst();
               // p.deletelast();
                p.deletemid2();
                p.print();
            
	}
        
}
class check{
        Node head;
        Node tail;
        void add(int data){
                Node newnode=new Node(data);
                if(head==null){
                        head=newnode;
                        tail=newnode;
                        return;
                }
                tail.next=newnode;
                tail=newnode;
        }
        void addfirst(int data){
                Node newnode=new Node(data);
                if(head==null){
                        head=newnode;
                        return;
                }
                
                Node temp=head;
        while(temp.next!=null){
                temp=temp.next;
                
              }
               
                temp.next=newnode;
                newnode.next=temp;
        }
       
      public  void mid(){
                int size=0;
                Node temp=head;
                while(temp!=null){
                         size++;
                        temp=temp.next;
                       
                }
              int count=size/2;
              Node prev=null;
              Node curr=head;
              for(int i=0;i<count;i++){
                      prev=curr;
                      curr=curr.next;
              }
             prev.next=curr.next;
        }
        void deletefirst(){
                if(head==null){
                        head=head.next;
                }
                head=head.next;
             
        }
        void deletemid2(){
                Node prev=null; 
                Node curr=head;
                Node last=head;
                while(last!=null && last.next!=null){
                        last=last.next.next;
                       prev=curr;
                       curr=curr.next;
                }
                prev.next=curr.next;
        }
        void deletelast(){
                if(head==null){
                        head=head.next;
                }
                Node prev=null;
                Node curr=head;
                Node temp=head;
                while(curr.next!=null){
                        prev=curr;
                        curr=curr.next;
                       
                }
            prev.next=curr.next;
        }
        void print(){
                Node temp=head;
                while(temp!=null){
                        System.out.print(temp.data+" ");
                    temp=temp.next;
                }
        }
}
class Node{
        int data;
        Node next;
        Node(int data){
               this.data=data;
                this.next=null;
        }
}
