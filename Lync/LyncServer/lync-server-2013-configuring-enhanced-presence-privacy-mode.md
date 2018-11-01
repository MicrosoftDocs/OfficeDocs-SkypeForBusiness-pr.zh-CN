---
title: 配置增强状态隐私模式
TOCTitle: 配置增强状态隐私模式
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399028(v=OCS.15)
ms:contentKeyID: 49314588
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置增强状态隐私模式

 

_**上一次修改主题：** 2016-12-08_

使用增强的状态隐私模式，用户可以限制其状态信息，以便仅对 Lync 2013 联系人列表中列出的联系人可见。**New-CsPrivacyConfiguration** 和 **Set-CsPrivacyConfiguration** cmdlet 的 EnablePrivacyMode 参数可控制此选项。将 EnablePrivacyMode 设置为 True 时，用于将状态信息限制到某些联系人的选项将在 Lync 2013 状态选项中可用。将 EnablePrivacyMode 设置为 False 时，用户可以选择始终允许所有人查看其状态信息或选择遵从管理员将来对隐私模式所做的任何更改。

> [!Important]  
> Lync 2013 和 Lync 2010 隐私设置不适用于早期版本（Microsoft Office Communicator 2007 R2 或 Microsoft Office Communicator 2007）。如果允许早期版本的 Office Communicator 登录，则未获授权的用户可以查看 Lync 2013 用户的状态、联系人信息或图片。此外，如果 Lync 2013 用户稍后使用早期版本的 Communicator 登录，则会重置该用户的隐私设置。<br />
> 出于以上原因，在迁移方案中，启用增强状态隐私模式之前，请：
> <ul>
> <li><p>确保每个用户都已安装 Lync 2013。</p></li>
> <li><p>定义客户端版本策略规则以阻止早期版本的 Communicator 登录。</p></li>
> </ul>


## 启用增强状态隐私模式

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行以下命令：
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    上述命令可为组织中当前使用的所有隐私配置设置启用隐私模式。

## 另请参阅

#### 其他资源

[Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

