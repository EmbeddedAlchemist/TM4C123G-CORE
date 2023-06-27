# 板载调试器使用说明

板载调试器兼容DAP-LINK，连接了SWD(SWDIO, SWCLK, RST)和UART(TX0, RX0)信号，可以通过命令来配置这些信号的连接状态，以便使用外部调试器。您可以在调试器的虚拟串口中输出这些命令。

注意：无论UART信号是否启用，虚拟串口将始终存在，但关闭UART信号后不再响应命令之外的输入；若SWD信号被禁用，它将从调试器列表中消失，直到再次启用SWD信号。

## 命令

### DBG+RESET

复位调试器

### DBG+UPDATE

使调试器进入ISP模式，此时可以借助WCH的的编程工具为调试器烧录新固件

### DBG+SWD

- `DBG+SWD?` 查询SWD信号状态
- `DBG+SWD=ENABLE`使能SWD信号
- `DBG+SWD=DISABLE`失能SWD信号

### DBG+UART

- `DBG+UART?` 查询UART信号状态
- `DBG+SWD=UART`使能UART信号
- `DBG+SWD=UART`失能UART信号

### DBG+INFO

查询调试器信息