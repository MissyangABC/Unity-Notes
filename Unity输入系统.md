输入系统分为两套，旧的是InputManager，新的是InputSystem
## InputManager
##### Input.mousePosition
他是鼠标相对于屏幕的位置，例如，屏幕是1920 X 1080，则屏幕的最左下角为（0，0），最右上角为（1920，1080）
#### InputManager设置
- Dead 是一个阈值，任何小于该值的输入值，无论正负，都会被视为0，常用于摇杆。
- 