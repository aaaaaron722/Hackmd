# DFS and BFS Review
基於專題製作內容涵蓋此部分，因此做一個筆記，方便之後複習。


首先，先複習簡單的概念前、中、後序traversal：
- Pre-order(root-left-right)：簡單來說就是root為先，所以叫前序遍歷
- In-order(left-root-right)：root在中間，因此叫中序遍歷
- Post-order(left-right-root)：root在後，因此叫後序遍歷
### DFS(Depth First Search)深度優先搜尋
DFS就是基於pre-order這樣的概念延伸，實作上我們會用stack這種資料結構實作。
(Stack的特點是LIFO後進先出)
1. 從根節點壓進stack
2. pop掉最上層的元素
3. 加入相鄰的邊

![截圖 2025-02-21 下午2.28.57](https://hackmd.io/_uploads/HJuHT5r9Jl.png)
(圖片來源：[GreeksForGreeks](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/?ref=gcse_outind))

以這張圖為例，
把root壓入stack
> Stack:[0]
> Visited:[]

pop 0 and add the adjacent vertex
> Stack:[1, 2, 3]
> Visited:[0]

pop 1 and add the adjacent vertex
> Stack:[4, 5, 2, 3]
> Visited:[0, 1]

pop 4 
> Stack:[5, 2, 3]
> Visited:[0, 1, 4]

pop 5 
> Stack:[2, 3]
> Visited:[0, 1, 4, 5]

pop 2 and add the adjacent vertex
> Stack:[6, 3]
> Visited:[0, 1, 4, 5, 2]

pop 6
> Stack:[3]
> Visited:[0, 1, 4, 5, 2, 6]

pop 3 and add the adjacent vertex
> Stack:[7]
> Visited:[0, 1, 4, 5, 2, 6, 3]

pop 7
> Stack:[]
> Visited:[0, 1, 4, 5, 2, 6, 3, 7]

### 另一種無向圖上的用法
DFS常見在tree跟graph，因此還有另一種在undirected graph上的用法
![截圖 2025-02-21 下午2.43.47](https://hackmd.io/_uploads/SJzTlor9Je.png)
(圖片來源：[GreeksForGreeks](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/?ref=gcse_outind))

以此圖為例先遍歷0
pop 0 and mark 0 as visited
> Stack:[1, 2, 3]

pop 1 
> Stack:[2, 3]

pop 2 and put the adjacent into stack
> Stack:[4, 3]

pop 4
> Stack:[3]

pop 3
> Stack:[]

就完成了！
以上，先寫到這邊，有看到什麼重要的再補充。