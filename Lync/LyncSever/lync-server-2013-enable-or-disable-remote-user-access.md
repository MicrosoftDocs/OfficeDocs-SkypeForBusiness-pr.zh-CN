---
title: Lync Server 2013：启用或禁用远程用户访问
TOCTitle: 启用或禁用远程用户访问
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182586(v=OCS.15)
ms:contentKeyID: 49314280
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中启用或禁用远程用户访问

 

_**上一次修改主题：** 2013-02-23_

远程用户是组织内拥有持久 Active Directory 标识的用户。远程用户在没有连接到组织的网络时，通常使用虚拟专用网 (VPN) 从网络外部登录到 Lync Server。远程用户包括在家或在路上工作的员工以及其他远程工作者，如已被授予企业凭据的受信任供应商。如果为远程用户启用远程用户访问，支持的远程用户可通过 Internet 进行连接，而无需为了使用 Lync Server 与内部用户协作而使用 VPN 进行连接。

要支持远程用户访问，必须启用远程用户访问。启用远程用户访问即为整个组织启用。如果稍后要暂时或永久阻止远程用户访问，可以为组织将其禁用。可以使用本节中的步骤为组织启用或禁用远程用户访问。

> [!NOTE]  
> 启用远程用户访问仅指定运行“访问边缘”服务的服务器支持与远程用户进行通信，但至少还需配置一个策略来管理远程用户访问的使用，远程用户才能参与组织中的即时消息 (IM) 或会议。在一个策略级别应用的 Lync Server 策略设置可能会覆盖在另一个策略级别应用的设置。Lync Server 策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。 有关配置远程用户访问使用策略的详细信息，请参阅 <a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中配置策略以控制远程用户访问</a>。



## 为组织启用或禁用远程用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“联盟和外部访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”中，执行下列操作之一：
    
      - 要为组织启用远程用户访问，请选中“启用远程用户访问”复选框。
    
      - 要为组织禁用远程用户访问，请清除“启用远程用户访问”复选框。

6.  单击“提交”。

要使远程用户能够登录到运行 Lync Server 的服务器，还必须至少配置一个外部访问策略以支持远程用户访问。有关详细信息，请参阅部署文档或操作文档中的 [在 Lync Server 2013 中配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)。

## 使用 Windows PowerShell Cmdlet 启用或禁用远程用户访问

可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 管理远程用户访问。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。

## 启用远程用户访问

  - 要启用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## 禁用远程用户访问

  - 要禁用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

