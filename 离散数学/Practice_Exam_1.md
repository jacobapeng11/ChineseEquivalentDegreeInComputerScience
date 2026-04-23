# 离散数学与组合数学考前20天冲刺模拟试卷1

> 按 2023-2025 真题高频块重写，优先覆盖逻辑、集合与关系；所有数字公式统一写成 inline math。

## 一、选择题（每题2分，共10分）

1. “没有两个人指纹完全相同” 的存在量词表示为（）。
   A. $\forall x\forall y(x\neq y\rightarrow Fingerprint(x)\neq Fingerprint(y))$
   B. $\neg\exists x\exists y(x\neq y\land Fingerprint(x)=Fingerprint(y))$
   C. $\exists x\exists y(x\neq y\land Fingerprint(x)=Fingerprint(y))$
   D. $\forall x\exists y(x\neq y\land Fingerprint(x)=Fingerprint(y))$

2. 设 $A=\{\emptyset\}$，下列说法错误的是（）。
   A. $\emptyset\in P(P(A))$
   B. $\{\emptyset\}\in P(P(A))$
   C. $\{\{\emptyset\}\}\in P(P(A))$
   D. $\{\emptyset,\{\emptyset\},\{\{\emptyset\}\}\}\in P(P(A))$

3. 公式 $((p\to q)\land(q\to r))\to(p\to r)$ 的类型是（）。
   A. 矛盾式
   B. 重言式
   C. 可满足式但非重言式
   D. 既非重言也非矛盾

4. 若关系同时是等价关系和偏序关系，则它必然是（）。
   A. 空关系
   B. 恒等关系
   C. 全域关系
   D. 传递关系

5. 设 $A,B$ 为集合，则 $A-B$ 等于（）。
   A. $A\cup B$
   B. $A\cap B$
   C. $A\cap\overline{B}$
   D. $\overline{A}\cap B$

## 二、填空题（每题2分，共10分）

1. 若 $|A|=5$，则 $|P(A)|=$ ________。
2. $\neg\exists xP(x)$ 等价于 ________。
3. 设划分 $\pi=\{\{1,2\},\{3,4,5\},\{6\}\}$，其对应等价关系共有 ________ 个有序对。
4. 只用联结词 $↓$ 表示 $P\land Q$ 的结果是 ________。
5. $m$ 个男生和 $m$ 个女生排成一列且女生在最前一位、男女相间时，排列数是 ________。

## 三、计算题（每题5分，共10分）

1. 用谓词逻辑写出“没有两个人指纹完全相同”的两种形式。
2. 设 $A=\{\emptyset\}$，求 $P(P(A))$ 的全部元素和元素个数。

## 四、证明题（每题5分，共10分）

1. 证明 $(A-B)-C=(A-C)-(B-C)$。
2. 证明二项式恒等式 $\sum_{i=0}^{k} C(m,i)C(n,k-i)=C(m+n,k)$。

## 参考答案

1. B。等价的否定存在式，正是 2024-2025 真题同类表达。
2. D。$P(P(A))$ 里只有 4 个元素，D 含 3 个元素，不是其子集。
3. B。假言三段论成立，所以是重言式。
4. B。等价关系要求对称，偏序关系要求反对称，两者兼得只能是恒等关系。
5. C。集合差就是与补集的交。
6. $32$。
7. $\forall x\neg P(x)$。
8. $14$，因为 $2^2+3^2+1^2=14$。
9. $(P↓P)↓(Q↓Q)$。
10. $(m!)^2$。
11. 可写为 $\neg\exists x\exists y(x\neq y\land Fingerprint(x)=Fingerprint(y))$，也可写为 $\forall x\forall y(x\neq y\rightarrow Fingerprint(x)\neq Fingerprint(y))$。
12. $P(P(A))=\{\emptyset,\{\emptyset\},\{\{\emptyset\}\},\{\emptyset,\{\emptyset\}\}\}$，共 4 个元素。
13. 取任意 $x$，若 $x\in(A-B)-C$，则 $x\in A, x\notin B, x\notin C$，所以 $x\in(A-C)-(B-C)$；反向同理。
14. 按从 $m$ 个元素里选 $i$ 个、从 $n$ 个元素里选 $k-i$ 个的分类计数即可。
