## 思路

使用一个辅助栈来保存

进栈时，如果x比辅助栈的栈顶元素大，不需要任何操作；如果比辅助栈的栈顶元素小或相等，则入栈

出栈时，如果辅助栈栈顶元素与栈的栈顶元素相等，就一起出栈，否则不用出栈。



```c++
class MinStack {
public:
    /** initialize your data structure here. */\
    
    stack<int> stk1;
    stack<int> stk2;

    MinStack() {

    }
    
    void push(int x) {
        stk1.push(x);
        if (stk2.empty() || x <= stk2.top())
            stk2.push(x);
    }
    
    void pop() {
        if (stk1.top() == stk2.top())
            stk2.pop();
        stk1.pop();
    }
    
    int top() {
        return stk1.top();
    }
    
    int min() {
        return stk2.top();
    }
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(x);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->min();
 */

//调用 min、push 及 pop 的时间复杂度都是 O(1)
//空间复杂度O(n)
```

