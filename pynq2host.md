# Pynq连接电脑

在配置文件/etc/networks/interface中修改网络配置
```
auto lo    
iface lo inet loopback
#不用fpga时
#iface eno1 inet dynamic 
#                                                                                                                              
#用fpga通信时
iface eno1 inet static
   address 192.168.2.1
   netmask 255.255.255.0
```

但有时这个配置文件不管用．可以直接在terminal下使用如下命令：
```
ifconfig eno1 up
ifconfig eno1 192.168.2.1
```

如此电脑和FPGA就可以ping通了．
```
ping 192.168.2.1　#可以ping通后，ssh链接
ssh xilinx@192.168.2.1
```
