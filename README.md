# Array
This is my git repo with Array data structure codes.

/import java.util.ArrayList;
//public class array{
   /*  public static void main(String args[]){

        ArrayList<Integer>al=new ArrayList<>();
      //  ArrayList<Integer>al1=new ArrayList<>(10);
       al.add(10);
       al.add(20);
       System.out.println(al);
    }
       */

       /* 

       //INSERT OPERATION..........


    public static int insert(int arr[],int n,int x,int capacity,int pos){
      
        if(n==capacity){
            return n;
        }
        int idx=pos-1;
        for(int i=n-1;i>=idx;i--){
            arr[i+1]=arr[i];
        }
        arr[idx]=x;
        return(n+1);
    }
    public static void main(String args[]){

        int arr[]=new int[5],capacity=5,n=3;
        arr[0]=10;arr[1]=20;arr[2]=30;

        System.out.println("Before Insertion");

        for(int i=0;i<n;i++){
 
            System.out.println(arr[i]+" ");
        }
         System.out.println();
         
         int x = 7, pos = 2;
 
        n = insert(arr, n, x,capacity, pos);
 
        System.out.println("After Insertion");
 
        for(int i=0; i < n; i++)
        {
                System.out.print(arr[i]+ " ");
        }
     } 

}
     */

     //DELETE OPERATION

     /*  import java.util.*;
     public class array{

        public static int delete(int arr[],int x,int n){

            int i=0;
            for( i=0;i<n;i++){
                if(arr[i]==x){
                    break;
                }
            }
                for(int j=i;j<n-1;j++){
                    arr[j]=arr[j+1];
                }
            
            return(n-1);
        }

        public static void main(String args[]){

            int arr[]={10,15,20,25,30},x=20,n=5;
            System.out.println("before deletion");
            for(int i=0;i<n;i++){
                System.out.println(arr[i]);
            }
            System.out.println("");

            n=delete(arr, x, n);
            System.out.println("after deletion");

            for(int i=0;i<n;i++){
                System.out.println(arr[i]);

            }


        }
     }
        */        
     /*   
     1.Largest ELement in an array

        import java.util.*;
        public class array{

            public static void largest(int arr[],int n,int assume){

                for(int i=0;i<n;i++){
                    if(arr[i]>assume){
                        assume=arr[i];
                    }
                }
                System.out.println(assume);

            }

            public static void main(String args[]){

                int assume=Integer.MIN_VALUE;
                int arr[]={10,20,30,40,50};
                int  n=5;
                largest(arr, n,assume);

            }
        } 
        

        
        //second largest & second smallest
        import java.util.*;
        public class array{
            public static void largestsmallest(int arr[],int n){

                if(n==0 || n==1){
                    System.out.println("-1");
                    System.out.println("");
                    System.out.println("\n");}

                    int small=Integer.MAX_VALUE;
                    int second_small=Integer.MAX_VALUE;
                    int largest=Integer.MIN_VALUE;
                    int second_largest=Integer.MIN_VALUE;
                
                    for(int i=0;i<n;i++){
                        small=Math.min(small,arr[i]);
                        largest=Math.max(largest,arr[i]);
                    }
                    for(int i=0;i<n;i++){
                    if(arr[i]<second_small && arr[i]!=small)
                    {
                        second_small=arr[i];
                                            }
                if(arr[i]>second_largest && arr[i]!=largest){
                    second_largest=arr[i];
                }
    
                }
            
         System.out.println("second smallest "+ second_small);
         System.out.println("second largest "+ second_largest);
    }

            public static void main(String args[]){

                int arr[]={1,1,2,3,4,5,6,7};
                int n=arr.length;
                largestsmallest(arr, n);

            }
        } 
    

    //optimised approach for largest element 

     import java.util.*;
     public class array{
        public static int second_largest(int arr[],int n){

            int res=-1, largest=0;

            for(int i=1;i<n;i++){
                if(arr[i]>arr[largest]){
                    res=largest;
                    largest=i;
                }
                else if(arr[i]!=arr[largest]){
                    if(res==-1 || arr[i]>arr[res]){
                        res=i;
                    }
                }
            }
            return res;
        }
        public static void main(String args[]){
            int arr[]={5,11,10,20};
            int n=arr.length;
            System.out.println(second_largest(arr, n));
            

        }
     }
        */
        import java.util.*;
        public class array{
          
            //problem 1:sorted or not
            public static boolean sortedornot(int arr[],int n){

                for(int i=1;i<n;i++){
                    if(arr[i]<arr[i-1])
                    return false;
                }
                return true;
            }
            //problem 2:reverse the array
            public static void reverse(int arr[],int n){

                int low=0,high=n-1;
                while(low<high){

                    int temp=arr[low];
                    arr[low]=arr[high];
                    arr[high]=temp;
                    low++;
                    high--;
                }
                for(int i=0;i<n;i++){
                    System.out.println(arr[i]);
                }

            }

            //problem 3:Remove Duplicates from Array

            public static int duplicates(int arr[],int n){

                int res=1;
                for(int i=res;i<n;i++){
                    if(arr[i]!=arr[res-1]){
                       
                        arr[res]=arr[i];
                        res++;
                    }
                }
                return res;
            }

            //problem 4:Move Zeros to End

            public static void movezero(int arr[],int n){

                int count=0;
                for(int i=0;i<n;i++){

                    if(arr[i]!=0){
                        arr[count]=arr[i];
                        count++;
                    }
                }
                while(count<n){
                    arr[count]=0;
                    count++;
                }
            }

            //problem 5:left rotate an arrray by one

            public static void rotatebyone(int arr[],int n){

                int temp=arr[0];
                for(int i=1;i<n;i++){

                    arr[i-1]=arr[i];
                }
                arr[n-1]=temp;
                for(int i=0;i<n;i++){
                    System.out.println(arr[i]);
                }

            }
            //problem 6:left rotate array by d
            public static void rotatebyd(int arr[],int n,int d){
                reversealgo(arr,0,d-1);
                reversealgo(arr,d,n-1);
                reversealgo(arr, 0,n-1);
            }
            public static void reversealgo(int arr[],int low,int high){

                while(low<high){
                   int temp=arr[low];
                   arr[low]=arr[high];
                   arr[high]=temp;
                   low++;
                   high--;
                }

            }
            //problem 7:leaders in an array
            public static void leaders(int arr[]){
                int n=arr.length;
                int curr_leader=arr[n-1];
                System.out.println(curr_leader);

                for(int i=n-2;i>=0;i--){
                    if(curr_leader<arr[i]){
                        curr_leader=arr[i];
                        System.out.println(curr_leader);
                    }

                }
            }

            //problem 8:maximum difference 
            public static int maxdifference(int arr[]){
                int n=arr.length;

                int res=arr[1]-arr[0];
                int minval=arr[0];
                for(int j=1;j<n;j++){

                    res=Math.max(res,arr[j]-minval);
                    minval=Math.min(minval,arr[j]);
                }
                return res;
            }

            //problem:9  frequencies in a sorted array

            //problem :10  buy sell stocks

            public static int stocks(int price[]){

                int profit=0,n=price.length;
                for(int i=1;i<n;i++){
                    if(price[i]>price[i-1]){

                        profit+=price[i]-price[i-1];
                    }
                }
                return profit;
            }

            //problem 11:Trapping rainwater problem

            public static int rainwater(int arr[]){

                int res=0;
               int n=arr.length;
                int lmax[]=new int[n];
                int rmax[]=new int[n];
                lmax[0]=arr[0];
                for(int i=1;i<n;i++){
                    lmax[i]=Math.max(arr[i], lmax[i-1]);
                }
                rmax[n-1]=arr[n-1];
                for(int i=n-2;i>=0;i--){
                    rmax[i]=Math.max(arr[i], rmax[i+1]);

                }
                for(int i=1;i<n-1;i++){
                    
                    res+=Math.min(lmax[i],rmax[i])-arr[i];
                }
                  return res;

            }

            //problem 12:consecutive 1s

            public static void countofones(int arr[]){

                int res=0,curr=0;
                 int n=arr.length;
                for(int i=0;i<n;i++){

                    if(arr[i]==0){
                        curr=0;
                    }
                    else{
                        curr++;
                    }
                    res=Math.max(res,curr);
                }
                  System.out.println(res);
            }

            //problem 13: maximum subarray 
            public static int maxsubarray(int arr[]){

                int n=arr.length;

                int max=arr[0];
                int res=arr[0];
                for(int i=0;i<n;i++){

                    max=Math.max(max+arr[i],arr[i]);
                    res=Math.max(res,max);
                }
                return max;
            }

            //problem 14:maximum even odd subarray

            public static int evenoddsubarray(int arr[])
            {
                int n=arr.length;
                int res=1;
                int curr=1;

                for(int i=1;i<n;i++){

                    if((arr[i]%2==0 && arr[i-1]%2!=0)||(arr[i]%2!=0 && arr[i-1]%2==0))
                    {
                        curr++;
                        res=Math.max(res,curr);
                    }
                    else{
                        curr=1;
                    }
                }
                return res;
            }
            //problem 15: Maximum circular subarray sum

            public static int normalmaxsum(int arr[]){
                
                int n=arr.length;
                int res=arr[0];
                int maxending=arr[0];

                for(int i=1;i<n;i++){

                    maxending=Math.max(maxending+arr[i], arr[i]);
                    res=Math.max(maxending, res);

                }
                return res;
            }
            public static int overallmaxsum(int arr[]){

                
                int max_normal=normalmaxsum(arr);
                int n=arr.length;
                if(max_normal<0){

                    return max_normal;
                
                    int arr_sum=0;

                    for(int i=0;i<n;i++)
                    {
                        arr_sum+=arr[i];
                        arr[i]=-arr[i];
                    }

                    int max_circular=arr_sum + normalmaxsum(arr);

                    return Math.max(max_circular, max_normal);

                }
            }

            //problem 16:majority element[count >n/2] (moores algo )

            public static int majority(int arr[]){

                int n=arr.length;
                int count =1;
                int res=0;

                for(int i=1;i<n;i++){

                    if(arr[res]==arr[i]){
                        count ++;
                    }
                    else{
                        count --;
                    }

                    if(count== 0){
                        count =1;
                        res=i;
                    }
                }

                count=0;

                for(int i=0;i<n;i++){

                    if(arr[res]==arr[i]){

                        count++;
                    }

                }
                if(count<=n/2)
                return -1;

                return res;
                
            }

            //problem 17: Minimum flips required

            public static void flips(int arr[],int n){

                for(int i=1;i<n;i++){

                    if(arr[i]!=arr[i-1]){

                        if(arr[i]!=arr[0]){
                        System.out.print(" from " + i + " to ");
                        }
                        else
                        {
                            System.out.print(i-1);
                        }
                    }
                }
                if(arr[n-1]!=arr[0]){
                    System.out.println(n-1);
                }
            }   
            
            //problem 18 :  Sliding window technique
            public static int slidingwindow(int arr[],int n,int k){

                int curr=0;
                for(int i=0;i<k;i++)
                    curr+=arr[i];
                    int max_sum=curr;

                    for(int i=k;i<n;i++){

                        curr+=arr[i]-arr[i-k];
                        max_sum=Math.max(max_sum, curr);
                    }
                 return max_sum;

            }

            // problem 19: subarray with given sum (naive solution)[0n2]
            public static boolean givensum(int arr[],int n,int sum){

                
                for(int i=0;i<n;i++){
                    int curr=0;
                    for(int j=i;j<n;j++){
                      curr+=arr[j];
                    System.out.println(curr);
                    if(sum==curr){
                        return true;
                    }
                }
            }
                    return false;
                }
                //optimised solution in code

                //problem 20: perfix sum (Optimised Code )

                public static int prefixsum(int ps[],int l,int r){

                    int n=ps.length;

                    if(l==0)
                    return ps[r];

                    return ps[r]-ps[l-1];


                }
                //problem 21:Equilibirium point
                 public static boolean Equilibirium(int arr[]){

                    int sum=0;
                    int n=arr.length;
                    for(int i=0;i<n;i++)
                        sum+=arr[i];
                    

                    for(int i=0;i<n;i++){
                        sum-=arr[i];
                      int ls=0;
                        if(ls==sum)
                        return true;

                        ls+=arr[i];
                }
                    return false;
            }
                



            public static void main(String args[]){
            
                //  int arr[]={1,2,3,4,5};
              // int arr[]={7,10,4,3,6,5,2};
                  //int arr[]={2,3,10,6,4,8};
                //  int n=arr.length;
                 // System.out.println(sortedornot(arr, n));
                // reverse(arr, n);

               /*  System.out.println("before removal");
                for(int i=0;i<n;i++){
                    System.out.println(arr[i]);
                }
                n=duplicates(arr, n);
                System.out.println("after removal of duplicates");
                for(int i=0;i<n;i++){

                    System.out.println(arr[i]);*/

                //   movezero(arr, n);

                 //for(int i=0;i<n;i++){
                   // System.out.println(arr[i]);

                  // rotatebyone(arr, n);
                      
                /*   int d=2;
                 rotatebyd(arr, n, d);
                 for(int i=0;i<n;i++){
                    System.out.println(arr[i]);*/
                   // leaders(arr);

                  // System.out.println(maxdifference(arr));

                  int price[]={7,1,5,3,6,4};
                  System.out.println("actual profit" +stocks(price));

               //  int arr[]={1,1,1,1,0,1,0,1};
                 
                // System.out.println(rainwater(arr));
               // System.out.println(countofones(arr));

             //  countofones(arr);

            // int arr[]={-3,8,-2,4,-5,6};
             //System.out.println(maxsubarray(arr));

           //  int arr[]={1,2,3,4,5,6};
            // System.out.println(evenoddsubarray(arr));
  
           // int arr[] = {8, -4, 3, -5, 4}, n = 5;
                 
           // System.out.println(overallmaxSum(arr));


          // int arr[]={8,8,6,6,6,4,6};
           //System.out.println(majority(arr));

          // int arr[]={0,0,1,1,0,0,1,1,0};
          // int n=9;
           //flips(arr, n);

         //  int arr[]={1,8,30,-5,20,7};
         //  int k=3;
         //  int n=6;
          // int sum=7;
           //System.out.println(slidingwindow(arr, n, k));
          //   System.out.println(givensum(arr,n,sum));

                    
           //  int arr[]={2, 8, 3, 9, 6, 5, 4};
        
        //     int n=7;
          //    int ps[];
            // ps = new int[n];
             //ps[0] = arr[0];
        
          //   for(int i=1; i<n; i++)
            //   ps[i] = ps[i-1]+ arr[i];
              //      System.out.println(prefixsum(ps, 1, 3));

              //int arr[]={-7,1,5,2,-4,3,0};
              //System.out.println(Equilibirium(arr));

                 }

        }

