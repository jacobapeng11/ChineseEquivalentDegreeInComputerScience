# 离散数学与组合数学考前20天冲刺模拟试卷1 - 独立答案版

> 对应 [Practice_Exam_1.md](Practice_Exam_1.md)，包含详细解答与本卷套路总结。

## 一、选择题详解

1. 选 B。原句“没有两个人指纹完全相同”最直接的存在量词否定形式就是“并不存在两个不同的人指纹相同”，即 $\neg\exists x\exists y(x\neq y\land Fingerprint(x)=Fingerprint(y))$。

2. 选 D。先算 $A=\{\emptyset\}$，则 $P(A)=\{\emptyset,\{\emptyset\}\}$，再得 $P(P(A))=\{\emptyset,\{\emptyset\},\{\{\emptyset\}\},\{\emptyset,\{\emptyset\}\}\}$。选项 D 只写出了其中 3 个元素，漏掉了 $\{\emptyset,\{\emptyset\}\}$，所以错误。

3. 选 B。该式是典型的假言三段论：由 $p\to q$ 和 $q\to r$ 可以推出 $p\to r$，因此对所有赋值都为真，是重言式。

4. 选 B。等价关系给出对称性，偏序关系给出反对称性。若同一个关系同时满足这两点，则只可能出现 $a=b$ 的情形，也就是恒等关系。

5. 选 C。集合差的定义就是“在 $A$ 中但不在 $B$ 中”，即 $A-B=A\cap\overline{B}$。

## 二、填空题详解

1. 答案：$32$。因为 $|P(A)|=2^{|A|}=2^5=32$。

2. 答案：$\forall x\neg P(x)$。这是 $\neg\exists xP(x)$ 的标准等价式。

3. 答案：$14$。等价类的有序对数等于各块大小平方和，所以 $2^2+3^2+1^2=14$。

4. 答案：$(P↓P)↓(Q↓Q)$。先用 $P↓P=\neg P$、$Q↓Q=\neg Q$，再由德摩根律得 $P\land Q=\neg(\neg P\lor\neg Q)$。

5. 答案：$(m!)^2$。女生位置固定在前、后交替，女生内部有 $m!$ 种排法，男生内部也有 $m!$ 种排法，相乘即可。

## 三、计算题详解

1. 设 $M(x)$ 表示“$x$ 是人”，$F(x,y)$ 表示“$x$ 与 $y$ 指纹相同”。

   可写成两种常见形式：
   $\forall x\forall y\bigl((M(x)\land M(y)\land x\neq y)\to \neg F(x,y)\bigr)$
   和
   $\neg\exists x\exists y\bigl(M(x)\land M(y)\land x\neq y\land F(x,y)\bigr)$。

   这两种写法本质上是同一件事：不存在两个不同的人指纹相同。

2. 先算 $P(A)$。因为 $A=\{\emptyset\}$，所以 $P(A)=\{\emptyset,\{\emptyset\}\}$。再对它取幂集，得到
   $P(P(A))=\{\emptyset,\{\emptyset\},\{\{\emptyset\}\},\{\emptyset,\{\emptyset\}\}\}$。

   因此全部元素个数是 $4$。

## 四、证明题详解

1. 证明 $(A-B)-C=(A-C)-(B-C)$。

   先证左边包含于右边。取任意 $x\in(A-B)-C$，则 $x\in A-B$ 且 $x\notin C$。于是 $x\in A$、$x\notin B$、$x\notin C$，所以 $x\in A-C$。又因为 $x\notin B$ 且 $x\notin C$，故 $x\notin B-C$，于是 $x\in(A-C)-(B-C)$。

   再证右边包含于左边。取任意 $x\in(A-C)-(B-C)$，则 $x\in A-C$ 且 $x\notin B-C$。于是 $x\in A$ 且 $x\notin C$。若 $x\in B$，又因 $x\notin C$，就会有 $x\in B-C$，与 $x\notin B-C$ 矛盾，所以 $x\notin B$。于是 $x\in A-B$，再结合 $x\notin C$，得到 $x\in(A-B)-C$。

   两边互相包含，故等式成立。

2. 证明 $\sum_{i=0}^{k}C(m,i)C(n,k-i)=C(m+n,k)$。

   这是最典型的分类计数题。把 $m+n$ 个元素分成前 $m$ 个和后 $n$ 个两组，从中选 $k$ 个时，先从前 $m$ 个中选 $i$ 个，再从后 $n$ 个中选 $k-i$ 个。对所有可能的 $i$ 求和，就得到左边；而直接从 $m+n$ 个元素中选 $k$ 个，方法数就是右边 $C(m+n,k)$。两边都在数同一件事，所以恒等式成立。

## 本卷套路总结

- 逻辑题先把“没有/并不存在”翻成否定存在式，通常比直接写全称更稳。
- 幂集题先把底层集合展开一遍，别急着套公式，先看元素到底有哪些。
- 集合恒等式优先用元素法，左右两边各做一次包含关系。
- 组合恒等式优先想“分类计数”，尤其是 $m+n$ 里取 $k$ 的题。
