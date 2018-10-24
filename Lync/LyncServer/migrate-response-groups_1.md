---
title: 迁移响应组
TOCTitle: 迁移响应组
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204931(v=OCS.15)
ms:contentKeyID: 49312967
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移响应组

 

_**上一次修改主题：** 2012-10-19_

在将您的用户移到 Lync Server 2013 池后，您可以迁移响应组。迁移响应组包括复制代理组、队列、工作流和音频文件，以及将 响应组联系对象从旧版部署移到 Lync Server 2013 池。在迁移旧版响应组后，对响应组的呼叫由 Lync Server 2013 池中的 响应组应用程序处理，而不再由旧版池处理。

> [!NOTE]  
> 虽然您可以在将所有用户移到 Lync Server 2013 池之前迁移响应组，但我们建议您首先移动所有用户。特别是，作为响应组代理的用户在移到 Lync Server 2013 池之前，将不具有新特性的完整功能。


在迁移响应组之前，您必须已部署包括响应组应用程序的 Lync Server 2013 池。响应组应用程序默认情况下在您部署企业语音时进行安装和激活。您可以通过运行 **Get-CsService–ApplicationServer** cmdlet 来确保安装了响应组应用程序。

> [!NOTE]  
> 在迁移旧版响应组之前，您可以在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组。


要将响应组从旧版池迁移到 Lync Server 2013，需要运行 **Move-CsRgsConfiguration** cmdlet。在运行 **Move-CsRgsConfiguration** 之前，您必须先安装 Windows Management Instrumentation (WMI) Backward Compatibility 接口包。可通过运行 OCSWMIBC.msi 来安装此应用程序。OCSWMIBC.msi 位于安装介质上的 Setup 文件夹中。

> [!IMPORTANT]
> 响应组迁移 cmdlet 会移动整个池的 响应组配置。您不能选择特定组、队列或工作流进行迁移。


在迁移响应组后，您需要更新正式代理用于登录和注销其响应组的 URL，并使用 Lync Server 控制面板或 Lync Server 命令行管理程序 cmdlet 来验证是否成功移动了所有代理组、队列和工作流。

> [!CAUTION]
> 在迁移响应组时，将不会删除 Office Communications Server 2007 R2 响应组。请不要删除 Office Communications Server 2007 R2 响应组。如果删除了 Office Communications Server 2007 R2 响应组， Lync Server 2013 中的响应组将停止工作。


> [!IMPORTANT]
> 建议在停用池之前不要删除之前的部署中的任何数据。此外，强烈建议在迁移后立即导出响应组。如果 Office Communications Server 2007 R2 响应组被删除，您随后可以从备份还原响应组以便让 Lync Server 2013 响应组重新运行。


在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。

> [!IMPORTANT]
> 建议在停用旧池之前不要删除其中的任何响应组数据。


以下迁移 响应组配置的过程假定您的旧版池和 Lync Server 2013 池之间具有一对一关系。如果您打算在迁移和部署期间合并或拆分池，则需要规划哪个旧版池与哪个 Lync Server 2013 池对应。

## 迁移 响应组配置

1.  在安装介质的 Setup 文件夹中找到 OCSWMIBC.msi 并安装它。

2.  使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。

3.  打开 Lync Server 命令行管理程序。

4.  在命令行中键入：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  如果在 Office Communications Server 2007 R2 环境中对 Microsoft Office Communicator 2007 R2 部署了响应组选项卡，则从 Office Communicator 2007 R2 tabs.xml 文件中删除该选项卡。
    
    > [!NOTE]
    > 正式代理会在接收呼叫之前，先使用响应组选项卡登录其响应组。如果部署了响应组选项卡，则在部署时为 Office Communicator 2007 R2 tabs.xml 文件选择位置。


6.  向用户提供代理登录和注销其响应组所需的更新 URL。
    
    > [!NOTE]
    > 该 URL 通常是 https://webpoolFQDN/RgsClients/Tab.aspx，其中 <em>webpoolFQDN</em> 是与刚迁移到 Lync Server 2013 的池关联的 Web 池的完全限定的域名 (FQDN)。
    
    > [!NOTE]
    > 在用户升级到 Lync 2013 后，不需要执行该步骤，因为可从 Lync 的“工具”菜单中找到该 URL。


## 使用 Lync Server 控制面板验证响应组迁移

1.  打开 Lync Server 控制面板。

2.  在左侧导航窗格中，单击“响应组”。

3.  在“工作流”选项卡上，验证 Office Communications Server 2007 R2 环境中的所有工作流是否都包含在该列表中。

4.  单击“队列”选项卡，并验证 Office Communications Server 2007 R2 环境中的所有队列是否都包含在该列表中。

5.  单击“组”选项卡，并验证 Office Communications Server 2007 R2 环境中的所有代理组是否都包含在该列表中。

## 使用 Cmdlet 验证响应组迁移

1.  打开 Lync Server 命令行管理程序。
    
    若要了解有关以下 cmdlet 的详细信息，请运行：
    
        Get-Help <cmdlet name> -Detailed

2.  在命令行中键入：
    
        Get-CsRgsAgentGroup

3.  验证 Office Communications Server 2007 R2 环境中的所有代理组是否都包含在该列表中。

4.  在命令行中键入：
    
        Get-CsRgsQueue

5.  验证 Office Communications Server 2007 R2 环境中的所有队列是否都包含在该列表中。

6.  在命令行中键入：
    
        Get-CsRgsWorkflow

7.  验证 Office Communications Server 2007 R2 环境中的所有工作流是否都包含在该列表中。

