---
title: 将 Microsoft SIP 处理语言 (MSPL) 应用程序标记为关键或非关键
TOCTitle: 将 Microsoft SIP 处理语言 (MSPL) 应用程序标记为关键或非关键
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182598(v=OCS.15)
ms:contentKeyID: 49314492
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Microsoft SIP 处理语言 (MSPL) 应用程序标记为关键或非关键

 

_**上一次修改主题：** 2012-11-01_

Microsoft SIP 处理语言 (MSPL) 服务器应用程序是只包含脚本的应用程序，这些应用程序使用 MSPL 脚本语言而不是 Microsoft Lync 2010 API。某些 MSPL 服务器应用程序指定为关键应用程序。如果脚本为关键脚本，则为了启动 Lync Server 2013，该脚本必须在系统启动过程中启动。如果该脚本在 Lync Server 运行期间出错，服务器不会关闭，但会停止向该脚本发送通信并会在事件日志中写入错误。

可以使用 Lync Server 控制面板将 Microsoft SIP 处理语言 (MSPL) 服务器应用程序标记为关键或取消标记。

并非所有脚本都支持此选项。例如，DefaultRouting 脚本标记为关键，无法为 DefaultRouting 更改此选项。

## 将 MSPL 服务器应用程序标记为关键或取消标记

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“拓扑”，然后单击“服务器应用程序”。

4.  在“服务器应用程序”页上，单击某个列标题对应用程序进行排序（如果需要），然后单击要修改的服务器应用程序。

5.  单击“操作”。

6.  单击“标记为关键”或“取消选择为关键”（前提是该脚本支持此选项）。

## 另请参阅

#### 任务

[启用或禁用 Microsoft SIP 处理语言 (MSPL) 服务器应用程序](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  

#### 概念

[在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### 其他资源

[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)

