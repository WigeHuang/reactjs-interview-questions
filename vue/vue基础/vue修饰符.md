### 事件修饰符
.stop 阻止事件继续传播

.prevent 阻止标签默认行为

.capture 使用事件捕获模式,即元素自身触发的事件先在此处处理，然后才交由内部元素进行处理

.self 只当在 event.target 是当前元素自身时触发处理函数

.once 事件将只会触发一次

.passive 告诉浏览器你不想阻止事件的默认行为

### v-model 的修饰符

.lazy 通过这个修饰符，转变为在 change 事件再同步

.number 自动将用户的输入值转化为数值类型

.trim 自动过滤用户输入的首尾空格

### 键盘事件的修饰符

.enter

.tab

.delete (捕获“删除”和“退格”键)

.esc

.space

.up

.down

.left

.right

### 系统修饰键

.ctrl

.alt

.shift

.meta

### 鼠标按钮修饰符

.left

.right

.middle
