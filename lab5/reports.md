```
import java.util.List;
public class StringSort{


    public static int search(List<String> list1, String target, int low, int high){
        if(low<=high) return -1;
        int mid = (low+high)/2;
        if(list1.get(mid) == target){
            return mid;
        }
        else if(list1.get(mid).compareTo(target)>0 ){
            return search(list1, target, low, mid-1);
        }
        else{
            return search(list1, target, mid+1, high);
        }
        
    
    }

    
}
```
