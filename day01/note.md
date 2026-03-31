# 一、MATLAB 主界面模块
MATLAB 主界面由**功能区、命令窗口、编辑器、工作区、当前文件夹、命令历史、帮助窗口**组成。

### 1. 功能区
- **主页**：新建脚本、打开文件、清空工作区
- **绘图**：快速生成各类图形
- **应用程序**：工具箱入口
- **编辑器**：代码编辑、调试

### 2. 命令窗口
输入命令、执行计算、显示结果，以 `>>` 为提示符。

### 3. 编辑器
编写 `.m` 脚本/函数，支持高亮、断点、单步运行。

### 4. 工作区
显示内存中所有变量的名称、大小、类型、值。

### 5. 当前文件夹
管理文件路径、查看脚本、运行程序。

### 6. 命令历史
记录执行过的命令，可重复执行。

### 7. 帮助窗口
查看函数文档、案例、语法说明。

---

# 二、常用系统命令（带示例）
## 1. `cd` — 切换工作目录
```matlab
cd C:\Users\Desktop  % 切换到桌面
```

## 2. `clear` — 清空工作区变量
```matlab
clear  % 清空所有变量
```

## 3. `dir` — 显示当前文件夹文件
```matlab
dir  % 列出所有文件
```

## 4. `path` — 查看/设置搜索路径
```matlab
path  % 查看路径
```

## 5. `help` — 查看函数帮助
```matlab
help plot  % 查看 plot 函数用法
```

## 6. `who` — 列出变量名
```matlab
who
```

## 7. `whos` — 详细列出变量信息
```matlab
whos
```

## 8. `save` — 保存变量
```matlab
save data.mat  % 保存为 data.mat
```

## 9. `load` — 加载变量
```matlab
load data.mat  % 读取变量
```

---

# 三、常用数学函数（带示例）
## 1. 绝对值/复数模
```matlab
abs(-5)       % 5
abs(3+4i)     % 5
```

## 2. 平方根
```matlab
sqrt(16)  % 4
```

## 3. 指数 e^x
```matlab
exp(1)  % 2.7183
```

## 4. 自然对数
```matlab
log(exp(1))  % 1
```

## 5. 常用对数
```matlab
log10(100)  % 2
```

## 6. 三角函数（弧度）
```matlab
sin(pi/2)   % 1
cos(pi)     % -1
```

## 7. 圆周率
```matlab
pi
```

---

# 四、向量创建（带示例）
## 1. 全 1 行向量
```matlab
ones(1,4)  % [1 1 1 1]
```

## 2. 全 0 列向量
```matlab
zeros(4,1)
```

## 3. 等差序列
```matlab
1:8  % [1 2 3 ... 8]
```

## 4. 自定义步长
```matlab
0:0.5:2  % [0 0.5 1 1.5 2]
```

## 5. 递减序列
```matlab
pi:-pi/3:0  % π, 2π/3, π/3, 0
```

---

# 五、矩阵操作（超详细）
## 1. 特殊矩阵
```matlab
eye(3)       % 3阶单位阵
ones(3)      % 3×3全1
zeros(3)     % 3×3全0
rand(3)      % 均匀随机
randn(3)     % 正态随机
magic(3)     % 3阶幻方
```

## 2. 矩阵索引
```matlab
A = [1 2 3;4 5 6;7 8 9];
A(2,:)       % 第2行
A(:,1)       % 第1列
A(2:3,2:3)   % 子矩阵
A(:)         % 展开为列
```

## 3. 矩阵运算
```matlab
A'           % 转置
inv(A)       % 逆
rank(A)      % 秩
trace(A)     % 迹
cond(A)      % 条件数
det(A)       % 行列式
tril(A)      % 下三角
triu(A)      % 上三角
```

## 4. 点运算（逐元素）
```matlab
A.*B  % 元素相乘
A./B  % 元素相除
A.^2  % 元素平方
```

---

# 六、元胞数组（带示例）
## 1. 创建
```matlab
a = {'matlab',20; ones(2,3), 1:10};
```

## 2. 访问元胞（返回 cell）
```matlab
a(1,2)
```

## 3. 提取数据（返回真实值）
```matlab
a{1,2}
```

## 4. 查看类型
```matlab
class(a{1,2})
```

---

# 七、字符串操作（带示例）
## 1. 定义字符串
```matlab
a = 'This is an example.';
```

## 2. 查看大小
```matlab
size(a)
```

## 3. 取子串
```matlab
a(1:4)  % 'This'
```

## 4. 反转字符串
```matlab
a(end:-1:1)
```

## 5. 转 ASCII 码
```matlab
double(a)
```

## 6. ASCII 转回字符
```matlab
char(double(a))
```

## 7. 大写转小写
```matlab
idx = a>='A' & a<='Z';
double_a = double(a);
double_a(idx) = double_a(idx)+32;
char(double_a)
```

## 8. 字符串拼接
```matlab
ab = [a(1:7),' Example']
```

---

# 八、方程与方程组求解
## 1. 高次方程求解
```matlab
syms x
eq = x^2 - 4 == 0;
solve(eq,x)
```

## 2. 线性方程组 Ax=B
```matlab
A = [1 2;3 4];
B = [5;6];
x = A\B
```

## 3. 多元方程组
```matlab
syms x y
eq1 = x+y==5;
eq2 = x-y==1;
solve([eq1,eq2],[x,y])
```

---

# 九、MATLAB 绘图（完整模板）
## 1. 基础二维绘图
```matlab
t = 0:0.1:2*pi;
y = sin(t);
plot(t,y,'r-','LineWidth',1.5);
xlabel('t'); ylabel('y');
title('sin(t)');
grid on;
```

## 2. 多曲线绘图
```matlab
plot(t,sin(t),'r',t,cos(t),'b');
legend('sin','cos');
```

## 3. 子图绘制
```matlab
subplot(2,2,1); plot(t,sin(t));
subplot(2,2,2); plot(t,cos(t));
subplot(2,2,3); plot(t,tan(t));
subplot(2,2,4); plot(t,exp(-t));
```

## 4. 三维曲线
```matlab
t = 0:0.1:10;
x = sin(t);
y = cos(t);
z = t;
plot3(x,y,z);
grid on;
```

## 5. 极坐标图
```matlab
theta = 0:0.1:2*pi;
rho = sin(2*theta);
polar(theta,rho);
```

## 6. 三维曲面
```matlab
[X,Y] = meshgrid(-2:0.1:2);
Z = X.^2 + Y.^2;
surf(X,Y,Z);
shading interp;
```

---

# 十、矩阵翻转与变形
## 1. 左右翻转
```matlab
fliplr(A)
```

## 2. 上下翻转
```matlab
flipud(A)
```

## 3. 旋转 90 度
```matlab
rot90(A)
```

## 4. 提取对角线
```matlab
diag(A)
diag(A,1)
diag(A,-1)
```
