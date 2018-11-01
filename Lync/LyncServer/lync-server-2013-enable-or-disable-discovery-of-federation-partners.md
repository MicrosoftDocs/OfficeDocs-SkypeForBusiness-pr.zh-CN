---
title: Lync Server 2013：启用或禁用联盟伙伴发现
TOCTitle: 启用或禁用联盟伙伴发现
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182550(v=OCS.15)
ms:contentKeyID: 49313615
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中启用或禁用联盟伙伴发现

 

_**上一次修改主题：** 2013-02-23_

在部署边缘服务器并为组织启用联盟时，应该已经指定了是否支持自动发现联盟伙伴域。使用本主题中的过程更改此配置。

> [!NOTE]  
> 以下过程假定您已为组织启用联盟。有关启用联盟的详细信息，请参阅部署文档或操作文档中的 <a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</a>。



## 为组织启用或禁用自动发现联盟域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”的“启用与联盟用户的通信”下，选中或清除“启用伙伴域发现”复选框以启用或禁用自动发现伙伴域。

6.  单击“提交”。

要使联盟用户能够与 Lync Server 部署中的用户进行协作，还必须至少配置一个外部访问策略以支持联盟用户访问。有关详细信息，请参阅部署文档或操作文档中的 [在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。有关控制特定联盟域的访问的详细信息，请参阅操作文档中的 [在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)、 [在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)和 [在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)。

## 使用 Windows PowerShell Cmdlet 启用或禁用联盟伙伴的发现

可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 管理联盟伙伴的发现。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。

## 启用联盟伙伴发现

  - 要启用联盟伙伴的发现，请将 **EnablePartnerDiscovery** 属性的值设置为 True ($True)。请注意，必须启用 DNS SRV 路由才能更改此属性值。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

## 禁用联盟伙伴发现

  - 要禁用联盟伙伴的发现，请将 **EnablePartnerDiscovery** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

