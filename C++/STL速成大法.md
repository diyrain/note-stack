# STL速记大法

## 一、vector

vector<int> aaa;

### 1.打印
- 新的for
```
for(int a : aaa)
{
    cout << a << endl;
}
```
- 传统for
- 迭代器 .begin()/.end()/.rbegin()/.rend()

### 2.访问
- []/.at()----还可修改元素
- .front()/.back()
- 迭代器:vector<int>::iterator it = v.begin(); 

.begin()/.end()/.rbegin()/.rend()

迭代器失效：插入/删除元素

### 3.添加元素
.push_back()末尾添加
### 4.删除元素
.pop_back()
### 5.其他
.size()

.empty()

.resize()

.insert()/.erase()配合迭代器

.find()  vector<int>::iterator pos = find(v.begin(), v.end(), 2);

.assign()  vec.assign(5, 10);  // 把 vec 变成 {10, 10, 10, 10, 10}

.swap()

## 二、列表list
开头末尾增加元素，但是不能直接跳到索引处--与向量的区别

### 1.打印元素
- for(int a: aaa)...
- 迭代器

### 2.访问
.front()/.back()--修改

### 3.添加
.push_front()/.push_back()

### 4.删除
.pop_front()/.pop_back()
### 5.其他
.size()

.resize()
    lt.resize(7, 6); //将size扩大为7，扩大的值为6
    lt.resize(2); //将size缩小为2

.empty()

.clear()

.insert()
    lt.insert(pos, 9); //在2的位置插入9
    lt.insert(pos, 2, 8); //在3的位置插入2个8
    lt.insert(pos, v.begin(), v.end()); //在1的位置插入v

.earse()
    lt.erase(pos);
    lt.erase(pos, lt.end()); 

.reverse()

.assign()

.swap()


## 三、栈stack
后进先出LIFO
### 1.初始化
//使用默认的适配器定义栈---deque
```
stack<int> st1;
```
//使用特定的适配器定义栈
```
stack<int, vector<int>> st2;
```
### 2.常用
.push()

.pop()

.top()

.empty()

.size()

.swap()
```
while (!s.empty()) {
        cout << s.top() << " ";  // 输出：3 2 1
        s.pop();
    }
```
## 四、队列queue
先进先出FIFO
### 1.定义
//使用默认的适配器定义队列--deque
```
queue<int> q1;
```
//使用特定的适配器定义队列
```
queue<int, vector<int>> q2;
```
### 2.常用
.push()

.pop()

.front()

.back()

.empty()

.size()

.swap()

## 五、集合set
唯一不重复
### 1.定义
默认升序，改变：set<int, greater<int>> numbers = {1, 7, 3, 2, 5, 9};

### 2.添加
.insert()
### 3.移除
.erase()

.clear()
### 4.其他
.size()

.empty()

## 六、映射map
键-值；键唯一；通过键访问

按键的升序排列
### 1.定义
```
map<string, int> people = { {"Bill", 19}, {"Steve", 32}, {"Elon", 26} };
```
### 2.访问--修改
- [键]
- .at(键) 
### 3.添加
- [键]=....值
- .insert({键，值})

如果我们尝试向映射添加两次 "Jack"，它只会保留第一个
### 4.移除
- .earse(键)
- .clear()
### 5.其他
- .size()
- .empty()
- .count(key)

检查特定元素是否存在。如果元素存在返回 1（true），否则返回 0（false）
### 6.访问
- 新的for
- .first + .second
```
map<string, int> people = { {"Bill", 19}, {"Steve", 32}, {"Elon", 26} };

for (auto person : people) {
  cout << person.first << " is: " << person.second << "\n";
}
```