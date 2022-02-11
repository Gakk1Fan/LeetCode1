## 思路

栈：后进先出

队列：先进先出

首先初始化两个栈stk1和stk2。

**出队：** 存入stk1中

**出队：**

1. 如果stk1和stk2都为空，返回-1
2. 如果stk2为空，则把stk1的数都放入stk2中；
3. 如果stk2不为空，则直接从stk2中取出一个数



## 代码

```c++
class CQueue {
public:
    stack<int> stk1;
    stack<int> stk2;
    CQueue() {
    }
    
    void appendTail(int value) {
        stk1.push(value);
    }
    
    int deleteHead() {
        if (stk1.empty() && stk2.empty()) return -1;
        if (stk2.empty()) {
            while (!stk1.empty()) {
                int x = stk1.top();
                stk1.pop();
                stk2.push(x);
            }
        }
        int ans = stk2.top();
        stk2.pop();
        return ans;
    }
};

/**
 * Your CQueue object will be instantiated and called as such:
 * CQueue* obj = new CQueue();
 * obj->appendTail(value);
 * int param_2 = obj->deleteHead();
 */

//时间复杂度O(1)
//空间复杂度O(n)
```

