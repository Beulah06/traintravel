# traintravel
package javaapplication30;
import java.util.Scanner;
public class JavaApplication30 {
    
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
       
        int ch;
        String day[]={"Monday","Tuesday","Wednesday"};
        double dept[]= {6.04,9.04,12.04,15.04,19.04};
        int pnum[]={22,119,64,177,21,22,111,87,193,22,11,107,93,162,42};
        System.out.println("enter the choice: ");
        ch=sc.nextInt();
        switch(ch)
        {
            //Display the data
         case 1:
        
         System.out.println("Day    "+"    Time    "+"number of passeners");
         for(int i=0,k=0;i<3;i++)
         {
           for(int j=0;j<5;j++,k++)
            System.out.println(day[i]+"     "+dept[j]+"       "+pnum[k]);
         }
         break;
             //Find the most popular train (day and time)

         case 2:
         int maxi=pnum[0];
         int ind = 0;
         for(int k=1;k<15;k++)
         {
            if(maxi<pnum[k])
            {
                maxi=pnum[k];
                ind = k;
            }
         }
         for(int i=0,k=0;i<3;i++)
         {
           for(int j=0;j<5;j++,k++)
           {
            if(k == ind)
                System.out.println("Most popular: "+day[i]+"     "+dept[j]);
           }
         }
         break;
             //Find the least popular train (day and time)
         case 3:
         int min=pnum[0];
         ind = 0;
         for(int k=1;k<15;k++)
         {
            if(min>pnum[k])
            {
                min=pnum[k];
                ind = k;
            }
         }
         for(int i=0,k=0;i<3;i++)
         {
           for(int j=0;j<5;j++,k++)
           {
            if(k == ind)
                System.out.println("Least popular: "+day[i]+"     "+dept[j]);
           }
         }
         break;
             // Find out whether the 6.04 train is more popular than the 9.04 train
         case 4:
         int sum1 = 0;
         int avg1= 0;
         for(int i=0,k=0;i<3;i++)
         {
           
           for(int j=0;j<5;j++,k++)
               if(dept[j]==6.04)
               {
                   sum1+=pnum[k];
//                    System.out.println(day[i]+"     "+dept[j]+"       "+pnum[k]);
               } 
         }
         avg1=sum1/3;
//        System.out.println(avg1);
        
         int sum2 = 0;
         int avg2= 0;
         for(int i=0,k=0;i<3;i++)
         {
           
           for(int j=0;j<5;j++,k++)
               if(dept[j]==9.04)
               {
                   sum2+=pnum[k];
                    //System.out.println(day[i]+"     "+dept[j]+"       "+pnum[k]);
               } 
         }
         avg2=sum2/3;
         //System.out.println(avg2);
         if(avg1>avg2)
            System.out.println("6.04 train is more popular than 9.04 train");
         else
            System.out.println("6.04 train is not popular than 9.04 train");
        break;
             //Find out whether the 6.04 train on Monday is more popular than the 6.04 train on Tuesday
        case 5:
        int l=0;
        int val[]={0,0};
        for(int i=0,k=0;i<2;i++)
        {
           
           for(int j=0;j<5;j++,k++)
           {
               
               if(dept[j]==6.04)
               {
                   
                    val[l]=pnum[k];
                    l+=1;
                   // System.out.println(day[i]+"     "+dept[j]+"       "+pnum[k]);
                    
               }
           }
        }
           if(val[0]==val[1])
                  System.out.println("both trains are equal");
           else if(val[0]>val[1])
                  System.out.println("6.04 train is more popular than 6.04 train on tuesday");
           else
                  System.out.println("6.04 train is not popular than 6.04 train on tuesday");
         break; 
            //Display a list of all trains (day, time) where passenger numbers were below 50
        case 6:
           
           System.out.println("Day    "+"    Time    "+"number of passeners");
           for(int i=0,k=0;i<3;i++)
           {
             for(int j=0;j<5;j++,k++)
             {
                 if(pnum[k]<50)
                   System.out.println(day[i]+"     "+dept[j]+"       "+pnum[k]);
             }
               
           }
         break;
            // Calculate the average number of passengers travelling on the 12.04 train over the three days (Monday, Tuesday, Wednesday)
         case 7 :
          int m=0;
          int valu[]={0,0,0};
          for(int i=0,k=0;i<3;i++)
          {
           
           for(int j=0;j<5;j++,k++)
           {
               
               if(dept[j]==12.04)
               {
                   
                    valu[m]=pnum[k];
                    m+=1;
                    //System.out.println(day[i]+"     "+dept[j]+"       "+pnum[k]);
                    
               }
           }
        
           
          }
          int ave;
          ave=(valu[0]+valu[1]+valu[2])/3;
          System.out.println("average:"+ave);
             
          break;
         case 8:
             System.exit(0);
         
     }      
   }
}
