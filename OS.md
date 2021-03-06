# OS
:::success
### 1.Race condition定義
- 多個行程同時存取或處理相同資料，而結果取決於存取順序時，就叫競爭狀況。

:::

:::info
### 2.入口區段與出口區段的定義
- 入口區段
> 行程必須要求允許，才可進入臨界區間。實現此要求的程式碼為入口區段
- 出口區段
> 臨界區間之後可能緊跟著出口區段
:::





::: warning
### 3.解決臨界區間(critical section)問題須滿足三項要求

- 互斥(mutual exclusion)
> 臨界區間有行程執行時，其他行程不能執行
- 進行(progress)
> 只有不在剩餘區間內的行程才能進去臨界區間
- 限制性的等待(bounded waiting)
> 在一個行程已要求進入臨界區間時，要求未被答應前，允許其他行程進入臨界區間的次數有個限制。
:::


:::danger
### 4.互斥鎖(mutex lock)
- 函數 acquire()
> 取得鎖
- 函數 release()
> 釋放鎖
- 缺點：會發生忙碌等待(busy waiting)
> 任何想進入臨界區的行程會在acquire()的地方不斷執行。
:::

:::success
### 5.號誌(semaphore)
- 函數 wait(S)
> S<=0的時候會等待
- 函數 signal(S)
> S+=1
- S預設皆為0
> 
:::

:::info
### 6.哲學家進餐問題
???
:::

:::success
### 7.死結的必要條件
- 互斥(mutual exclusion)
> 一次只有一個執行緒可使用此資源
- 占用與等候(hold and wait)
> 必須存在一個至少已佔用一個資源，且正等候其他執行緒占用的另外資源
- 不可搶先(no preemption)
> 資源不可被搶先
- 循環式等候(circular wait)
> 必須存在迴圈，Tn的要求的資源被Tn-1占用....
:::

:::info
### 8.預防死結
- 互斥(mutual exclusion)
> 無法解決，因為許多資源天生就是不可共用的 
- 占用與等候(hold and wait)
> 無法解決，會造成資源使用率過低和飢餓
- 不可搶先(no preemption)
> 無法解決，只適用於資源狀態能輕易被保存或稍後可恢復的情況
- 循環式等候(circular wait)
> 可解決，對所有資源安排一個線性順序
:::


:::info
### 9.資源的搶先
## 用資源的搶先消除死結，考慮三件事情
- 選擇犧牲者(select victim)
> 哪個資源或行程將被搶先
- 回撤(rollback)
> 被搶先的行程回到安全狀態
- 飢餓(starvation)
> 如何防止飢餓

:::


:::info
### 10.記憶體配置

- 最先配合
> 
- 最佳配合
> 
- 最差配合
> 

:::

:::warning
### 11.外部斷裂 內部斷裂

- 外部斷裂
> 記憶體的剩餘空間因被其他行程切割而造成不連續，這些區間大小不一，可能造成空間浪費
- 內部斷裂
> 行程額外要求自己不需要的空間，減少記憶體小碎塊的狀況

:::