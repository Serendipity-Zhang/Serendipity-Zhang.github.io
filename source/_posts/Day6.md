---
title: Day5:知识点记录
date: 2020-9-23
---

# 350 两个数组的交集 II  (indexOf检查是否另一个数组存在，哈希表记录元素出现的个数、序列优化循环)

- indexOf 检查是否在另一个数组中存在
```txt
遍历其中一个数组nums1,在另一个数组nums2 中是否存在该元素
- 存在放入到结果中，并在nums2中删除
- 不存在则不做任何操作
```
```javascript
const intersect = (nums1,nums2) => {
  let _result = [] //定义一个空数组
  for(let i = 0; i<nums1.length;i++>){
    let j =  nums2.indexOf(nums1[i])  //判断当前元素是否在nums2中出现 ,如果出现用j进行过存储索引
   //如果不出现为-1
   if(j >= 0 ){  //如果大于等于0证明出现了进行push
      _result.push(nums1[i]) 
      nums2.splice(j,1)  //删除nums2 中的数据 避免重复
   }
   return _result
  }
}
```