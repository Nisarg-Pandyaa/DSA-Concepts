# int[][] edges -> Adjacent Mtx (for dfs)
- let n = number of node, int[][] edges = {parent,child}
----

```java
List<Integer>[] graph = new ArrayList[n];

for(int i=0;i<n;i++){
       graph[i] = new ArrayList<>();
}

for(int[] arr : edges){
      graph[arr[0]].add(arr[1]);
}

return dfs(graph,0);
