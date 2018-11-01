---
title: 创建或修改 Lync Phone Edition 配置设置的集合
TOCTitle: 创建或修改 Lync Phone Edition 配置设置的集合
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49888456
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改 Lync Phone Edition 配置设置的集合

 

_**上一次修改主题：** 2013-02-23_

安装 Lync Server 时，您将获得 Lync Phone Edition 设置的全局集合。这些设置适用于您的部署中运行 Lync Phone Edition 的所有设备。您可以随时更改这些设置。还可以设置适用于特定站点中的设备的设置的新集合。站点设置优先于全局设置。

配置设置包含集合名称、范围（全局或站点）、SIP 安全设置、日志记录级别、语音服务质量 (QoS) 级别、电话锁定设置和电话锁定详细信息（即，a) 解锁个人标识号 (PIN) 所需花费的时间和 b) 电话在自行锁定之前保持空闲状态的时间长度）。

## 创建 Lync Phone Edition 配置设置集合或编辑现有集合的设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“设备配置”导航按钮。

4.  在“设备配置”页上，执行下列操作之一：
    
      - 若要创建新的 Lync Phone Edition 配置设置集合，请单击“新建”，选择一个站点，单击“确定”，再查看默认设置，然后根据需要进行任何更改。
    
      - 若要编辑某个现有集合中的任意设置，请依次单击该集合、“编辑”菜单和“显示详细信息”，然后进行更改。
        
        > [!TIP]  
        > 若要继续使用全局集合的默认设置，请依次单击全局集合、“编辑”菜单、“删除”和“确定”。这不会删除全局集合，而只是将设置重置为默认值。


5.  单击“提交”。

## 使用 Lync Server 命令行管理程序 cmdlet 创建新的 Lync Phone Edition 配置设置

还可以使用 Lync Server 命令行管理程序和 **New-CsUCPhoneConfiguration** cmdlet 创建 Lync Phone Edition 配置设置（仅在站点范围）。您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 创建使用默认值的新 Lync Phone Edition 配置设置

  - 此命令为 Redmond 站点创建一组新的 UC 电话配置设置：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新的配置设置集合将对其所有属性使用默认值。

## 在创建新的 Lync Phone Edition 配置设置时更改单个属性值

  - 若要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，默认情况下，若要创建需要电话锁定的 UC 电话配置设置的集合，请使用与以下内容类似的命令：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

## 在创建新的 Lync Phone Edition 配置设置时更改多个属性值

  - 可通过包含多个参数来修改多个属性值。例如，此命令强制电话锁定并将最小 PIN 长度设置为 8 位：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

有关详细信息，请参阅 [New-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUCPhoneConfiguration)。

## 另请参阅

#### 任务

[删除 Lync Phone Edition 配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[配置 Lync Phone Edition 的安全设置](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[强制电话锁定](lync-server-2013-enforce-phone-locking.md)

