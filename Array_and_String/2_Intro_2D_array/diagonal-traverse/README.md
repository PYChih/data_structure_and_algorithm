# 0112: Diagonal Traverse
- 想法:
    - 先對角線遍歷
- 觀察:
    - 每個對角線的下標和都一樣(1, 2, 3 ...)
        - 最後反而沒用到這個直接++--
- 需求:
    - 一個迴圈繞過所有對角線
        - 偶數次繞過要反轉
            - ``ivec.insert(ivec.end(), temp.begin(), temp.end())``
            - ``ivec.insert(ivec.end(), temp.rbegin(), temp.rend());``
        - 問題: ==總共繞(m+n-1)次==
            - 沒處理長方形case，這個裡面的loop會解掉
    - 一個迴圈跑一次對角線
        - ==這個下標不知道怎麼下==
        - row_index:
            - 第(num_col-1)個對角線前都是零
            - 第(num_col-1)個對角線後從1遞增
        - col_index:
            - 第(num_col-1)個對角線前從1遞增
            - 第(num_col-1)個對角線後固定是(num_col-1)
- corner case:
    - 全空矩陣: `matrix.size()==0`
    - 有一個空向量的向量

- 語法問題紀錄:
  - [x] insert的用法 