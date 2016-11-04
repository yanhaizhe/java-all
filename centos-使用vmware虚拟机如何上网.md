1、 宿主机的虚拟网关VMnet8的IP设置为自动获取。具体步骤为：右击点“属性”，然后选择IPV4那行，点击“属性"，更改成自动获取。

![](/assets/QQ截图20161104222501.png)

2、 同理，修改“本地连接”也为自动获取

![](/assets/QQ截图20161104222502.png)

3、 “虚拟机”-“设置”，网络适配器选为NAT

![](/assets/QQ截图20161104222810.png)

4、 “编辑”-“虚拟网络编辑器”选中VMnet8，点选NAT（与虚拟机共享主机IP地址），把DHCP勾上（那两个框都勾上）。

点击“应用”。

![](/assets/QQ截图20161104222919.png)

5、 开启宿主机（windows7）中的VMware DHCP Service 和VMware NAT Service服务。写个脚本省事儿

![](/assets/QQ截图20161104223024.png)

6、 再写个Linux脚本，如图 

7、 运行后如图，

这个脚本作用为：

关闭NetworkManager（service NetworkManager stop），重启network（service network restart），再启动

NetworkManager（service NetworkManager start）。【因为NetworkManager会对network重启造成影响，所以先关闭它，最后

这服务不启动也有影响，所以最后再启动它】



8、 最后测试网络连通情况 



