import java.util.*;
		public class Main{
			public static void main(String args[]){
				Scanner cin = new Scanner(System.in);
				
				int[] array = new int[10];
				int k=0;
				while(cin.hasNextInt()){
					array[k++] = cin.nextInt();
				}
				
				for(int i=0;i<array.length;i++){
					for(int j=i;j<array.length-1;j++){
						if(array[j]>array[j+1]){
							int temp = array[j+1];
							array[j+1] = array[j];
							array[j] = temp;
						}
					}
				}
				
				int[] ji = new int[10];
				int[] ou = new int[10];
				int m=0;
				int n=0;
				for(int i=0;i<array.length;i++){
					if(array[i]%2==0){
						ou[m++] = array[i];
					}else{
						ji[n++] = array[i];
					}
				}
				int max = m;
				if(n>m){
					max = n;
				}
				int[] res = new int[2*max-3];
				m=n=0;
				for(int i=0;i<res.length;i++){
					if(i%2==0){
						res[i] = ou[m++];
					}else{
						res[i] = ji[n++];
					}
				}
				for(int i=0;i<res.length;i++){
					System.out.println(res[i]);
				}
			}
			
		}
