# DSC_Lab_服务器用电安全指南
V1.0版本 2024/11/13 卢贺贤

## 入电线路 
位于空调顶部，插头规格为10A
![空调顶部](/image/input1.png)

位于空调底部，插头规格为16A
![空调底部](/image/input2.png)

位于座位底部，插头规格为10A
![座位底部](/image/input3.png)


## 机架正面
tip：TDP（热设计功耗）是衡量处理器在峰值负载下产生的最大热量的指标，用于指导散热系统设计，确保能够有效散热。<u>在配置电源和散热系统时，考虑到处理器的实际功耗和TDP，以确保系统的稳定运行</u>。

> ### RX340xd [🟢 绿色]
> - IP：192.168.1.17
> - CPU：Intel(R) Xeon(R) E-2224 CPU 
> - RAM：16G
> - TDP：80W（处理器）+ 160W（内存）+ 124W（硬盘）+ 8W（RAID控制器）+ 60W（风扇）+ 100W（主板和其他组件）= 🟢 532W
> ### RX740xd [🔴 红色]
> - IP：192.168.1.19
> - CPU：Intel(R) Xeon(R) Silver 4216 CPU *2
> - RAM：128G
> - GPU：Tesla P40 24G
> - GPU：NVIDIA GeForce RTX 3090 24G
> - 数据挂载：/data
> - TDP：200W（处理器）+ 160W（内存）+ 124W（硬盘）+ 8W（RAID控制器）+ 600W（GPU）+ 60W（风扇）+ 100W（主板和其他组件）= 🔴 1252W
> ### RX740xd [🟡 黄色]
> - IP：192.168.1.18
> - CPU：Intel(R) Xeon(R) Gold 6248R CPU @ 3.00GHz *2
> - RAM：256G
> - GPU：GeForce RTX 2080 Ti 11GB
> - 数据挂载：/data/data1
> - TDP：330W（处理器）+ 160W（内存）+ 124W（硬盘）+ 8W（RAID控制器）+ 250W（GPU）+ 60W（风扇）+ 100W（主板和其他组件）= 🟡 1022W
> ### RX750 [🔵 蓝色]
> - IP：192.168.1.100
> - CPU： Intel(R) Xeon(R) Gold 6330 CPU @ 2.00GHz *2
> - RAM：512G
> - GPU：NVIDIA A100-SXM4-80GB 
> - 数据挂载：/data
> - TDP：410W（处理器）+ 160W（内存）+ 124W（硬盘）+ 8W（RAID控制器）+ 400W（GPU）+ 60W（风扇）+ 100W（主板和其他组件）= 🔵 1262W

![座位底部](/image/server.png)


## OSD切换
> - ch1: [🔴 RX740xd] [ 2080 Ti ]
> - ch2: [🔵 RX750] [ A100 ]
> - ch7: [🟢 RX340] [ / ]
> - ch8: [🟡 RX740xd] [ 3090 Ti , P 40 ]
![OSD](/image/OSD.jpg)

## 机架背面
> ### 按照颜色区分电路
> - [🟡 RX740xd]
> - [🔵 RX750] 
> - [🟢 RX340+外围设备]
> - [🔴 RX740xd]
![OSD](/image/server-back.png)
