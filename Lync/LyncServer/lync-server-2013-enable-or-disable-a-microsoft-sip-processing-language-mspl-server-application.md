---
title: 启用或禁用 Microsoft SIP 处理语言 (MSPL) 服务器应用程序
TOCTitle: 启用或禁用 Microsoft SIP 处理语言 (MSPL) 服务器应用程序
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182573(v=OCS.15)
ms:contentKeyID: 49313981
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用或禁用 Microsoft SIP 处理语言 (MSPL) 服务器应用程序

 

_**上一次修改主题：** 2012-09-21_

可以使用 Lync Server 控制面板启用或禁用在 Lync Server 2013 环境中运行的 Microsoft SIP 处理语言 (MSPL) 服务器应用程序。这些应用程序是仅包含脚本的应用程序，使用脚本语言而非 Microsoft Lync 2013 Preview API。

并非所有脚本都能启用或禁用。例如，DefaultRouting 脚本为启用状态，无法为 DefaultRouting 更改此选项。

## 启用或禁用 MSPL 服务器应用程序

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“拓扑”，然后单击“服务器应用程序”。

4.  在“服务器应用程序”页上，单击某个列标题对应用程序进行排序（如果需要），然后单击要修改的服务器应用程序。

5.  单击“操作”。

6.  单击“启用应用程序”或“禁用应用程序”（前提是该脚本支持此选项）。

## 另请参阅

#### 任务

[将 Microsoft SIP 处理语言 (MSPL) 应用程序标记为关键或非关键](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  

#### 概念

[在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### 其他资源

[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)

