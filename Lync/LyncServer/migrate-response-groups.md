---
title: 迁移响应组
TOCTitle: 迁移响应组
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204854(v=OCS.15)
ms:contentKeyID: 49312680
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移响应组

 

_**上一次修改主题：** 2013-09-23_

在将您的用户移到 Lync Server 2013 池后，您可以迁移响应组。迁移响应组包括复制代理组、队列、工作流和音频文件，以及将 响应组联系对象从旧版部署移到 Lync Server 2013 池。在迁移旧版响应组后，对响应组的呼叫由 Lync Server 2013 池中的 响应组应用程序处理，而不再由旧版池处理。

> [!NOTE]  
> 虽然您可以在将所有用户移到 Lync Server 2013 池之前迁移响应组，但我们建议您首先移动所有用户。特别是，作为响应组代理的用户在移到 Lync Server 2013 池之前，将不具有新特性的完整功能。


在迁移响应组之前，您必须已部署包括响应组应用程序的 Lync Server 2013 池。响应组应用程序默认情况下在您部署企业语音时进行安装和激活。您可以通过运行 **Get-CsService –ApplicationServer** cmdlet 来确保安装了响应组应用程序。

> [!NOTE]  
> 在迁移旧版响应组之前，您可以在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组。


若要将旧版池中的响应组迁移到 Lync Server 2013，您必须运行 **Move-CsRgsConfiguration** cmdlet。

> [!IMPORTANT]
> 响应组迁移 cmdlet 会移动整个池的 响应组配置。您不能选择特定组、队列或工作流进行迁移。


在迁移响应组后，您需要使用 Lync Server 控制面板或 Lync Server 命令行管理程序 cmdlet 验证是否已成功迁移所有代理组、队列和工作流。

迁移响应组时，不会删除 Lync Server 2010 响应组。在迁移后使用 Lync Server 控制面板或 Lync Server 命令行管理程序管理响应组时，您会看到 Lync Server 2010 响应组和 Lync Server 2013 响应组。应仅对 Lync Server 2013 响应组应用更新。仅保留 Lync Server 2010 响应组以进行回滚。

> [!CAUTION]
> 在完成迁移并创建新的响应组之后，Lync Server 控制面板和 Lync Server 命令行管理程序将显示每个响应组的 Lync Server 2010 和 Lync Server 2013 版本。请勿使用 Lync Server 控制面板 或 Lync Server 命令行管理程序 删除 Lync Server 2010 响应组。如果删除，则迁移期间创建的对应响应组将停止工作。当您停用 Lync Server 2010 池时，Lync Server 2010 响应组将被删除。


> [!IMPORTANT]
> 建议在停用池之前不要删除之前的部署中的任何数据。此外，强烈建议在迁移后立即导出响应组。假使已删除 Lync Server 2010 响应组，您可以从备份中还原响应组以便再次运行 Lync Server 2013 响应组。


Lync Server 2013 引入了一种新的 响应组功能，称为“工作流类型”。“工作流类型”可以是“托管”的，也可以是“非托管”的。所有响应组都是使用设置为“非托管”的“工作流类型”和空管理员列表进行迁移的。

在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。

以下迁移 响应组配置的过程假定您的旧版池和 Lync Server 2013 池之间具有一对一关系。如果您打算在迁移和部署期间合并或拆分池，则需要规划哪个旧版池与哪个 Lync Server 2013 池对应。

## 迁移 响应组配置

1.  使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  将响应组和代理迁移到 Lync Server 2013 池之后，代理用来登录和注销的 URL 是 Lync Server 2013 URL，可以从“工具”菜单访问该 URL。提醒代理更新对新 URL 的所有引用（例如书签）。

## 使用 Lync Server 控制面板验证响应组迁移

1.  使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航窗格中，单击“响应组”。

4.  在“工作流”选项卡上，验证 Lync Server 2010 环境中的所有工作流是否都包含在该列表中。

5.  单击“队列”选项卡，并验证 Lync Server 2010 环境中的所有队列是否都包含在该列表中。

6.  单击“组”选项卡，并验证 Lync Server 2010 环境中的所有代理组是否都包含在该列表中。

## 使用 Lync Server 命令行管理程序 验证响应组迁移

1.  使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。
    
    若要了解有关以下 cmdlet 的详细信息，请运行：
    
        Get-Help <cmdlet name> -Detailed

3.  运行：
    
        Get-CsRgsAgentGroup

4.  验证 Lync Server 2010 环境中的所有代理组是否都包含在该列表中。

5.  运行：
    
        Get-CsRgsQueue

6.  验证 Lync Server 2010 环境中的所有队列是否都包含在该列表中。

7.  运行：
    
        Get-CsRgsWorkflow

8.  验证 Lync Server 2010 环境中的所有工作流是否都包含在该列表中。

