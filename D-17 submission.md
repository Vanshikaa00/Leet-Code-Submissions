## :zap: Question

>Given a non-empty array of integers, return the k most frequent elements.
```
Example 1:

Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]
Example 2:

Input: nums = [1], k = 1
Output: [1]
Note:

You may assume k is always valid, 1 ≤ k ≤ number of unique elements.
Your algorithm's time complexity must be better than O(n log n), where n is the array's size.
It's guaranteed that the answer is unique, in other words the set of the top k frequent elements is unique.
You can return the answer in any order.
```

## :peach: Solution

```
class Solution {
    public int[] topKFrequent(int[] nums, int k) {
         HashMap<Integer,Integer> map=new HashMap<>();
        
        for(int i:nums){
            map.put(i,map.get(i)==null?1:map.get(i)+1);
        }
        
    PriorityQueue<Integer> heap =
            new PriorityQueue<Integer>((n1, n2) -> map.get(n1) - map.get(n2));

    for (int n: map.keySet()) {
      heap.add(n);
      if (heap.size() > k)
        heap.poll();
    }

    int[] top_k =new int[heap.size()];
        int i=heap.size()-1;
    while (!heap.isEmpty())
      top_k[i--]=heap.poll();
    return top_k;
    }
}
```
