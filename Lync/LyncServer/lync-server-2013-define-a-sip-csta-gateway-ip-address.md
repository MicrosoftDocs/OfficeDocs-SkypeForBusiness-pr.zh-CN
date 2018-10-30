---
title: Lync Server 2013：定义 SIP/CSTA 网关 IP 地址
TOCTitle: 定义 SIP/CSTA 网关 IP 地址
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg602125(v=OCS.15)
ms:contentKeyID: 49313950
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址

 

_**上一次修改主题：** 2012-09-21_

如果 Lync Server 将使用传输控制协议 (TCP) 连接来连接到您部署的用于远程呼叫控制的 SIP/CSTA 网关，则必须在 拓扑生成器中定义该网关的 IP 地址。对于支持传输层安全性 (TLS) 连接的网关来说，这一步不是必需的。对于支持 TLS 连接的任何网关，您可以跳过此过程，并按照 [在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制](lync-server-2013-enable-lync-users-for-remote-call-control.md)中的步骤继续部署远程呼叫控制。

## 使用拓扑生成器定义 SIP/CSTA 网关 IP 地址

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

3.  选择相应的选项以下载现有拓扑。

4.  展开“受信任的应用程序服务器”节点。

5.  右键单击所创建的受信任应用程序池（如 [在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)中所述），然后单击“编辑属性”。

6.  清除“允许将配置数据复制到此池”复选框。

7.  单击“将服务用途限制为所选 IP 地址”。默认设置为“使用所有已配置的 IP 地址”。

8.  在“主 IP 地址”文本框中，输入 SIP/CSTA 网关的 IP 地址。

9.  要更新中央管理存储中的拓扑，请在控制台树中单击“Lync Server”，然后从“操作”窗格中单击“发布”。

## 另请参阅

#### 任务

[在 Lync Server 2013 中为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

