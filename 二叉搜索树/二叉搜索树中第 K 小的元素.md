# 230.二叉搜索树中第 K 小的元素
```javascript
var kthSmallest = function(root, k) {
  var res = null
  var rank = 0
  

  const traverse = (root, k) =>{
  if(!root){
    return
  }
  traverse(root.left, k)
  rank++
  if(k === rank){
    res = root.val
    return
  }
  traverse(root.right, k)
}
  traverse(root, k)
  return res
};




```

# 538.把二叉搜索树转换为累加树
```javascript
var convertBST = function(root) {
  let sum = 0
  const traverse = (root) => {
    if(!root) return
    traverse(root.right)
    sum += root.val
    root.val = sum
    traverse(root.left)
  }
  traverse(root)
  return root
};
```