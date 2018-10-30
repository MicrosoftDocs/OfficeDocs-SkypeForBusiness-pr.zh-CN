---
title: Lync Server 2013：使用 Cmdlet 反向执行域准备
TOCTitle: 使用 Cmdlet 反向执行域准备
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398071(v=OCS.15)
ms:contentKeyID: 49311804
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 Cmdlet 为 Lync Server 2013 反向执行域准备

 

_**上一次修改主题：** 2012-10-29_

使用 **Disable-CsAdDomain** cmdlet 可反向执行域准备步骤。

## 使用 cmdlet 反向执行域准备

1.  以 Domain Admins 组成员的身份登录域中的任何服务器。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    例如：
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    如果存在 Force 参数，域准备将会回滚，即使域中的一个或多个 前端服务器或 A/V 会议服务器已激活。如果不存在 Force 参数，并且域中的任何 前端服务器或 A/V 会议服务器 已激活，域准备回滚将被终止。
    
    > [!NOTE]
    > 参数 GlobalSettingsDomainController 用于指出存储全局设置的位置。如果设置存储在“系统”容器中（在全局设置尚未迁移到“配置”容器的升级部署中时通常是这种情况），则定义 Active Directory 林的根中的某个域控制器。如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 AD DS 中的任何域控制器。


## 另请参阅

#### 任务

[为 Lync Server 2013 运行域准备](lync-server-2013-running-domain-preparation.md)  

#### 其他资源

[为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)

