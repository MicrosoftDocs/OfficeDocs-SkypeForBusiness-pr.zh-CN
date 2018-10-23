---
title: Lync Server 2013：委派 Lync Server 2013 的管理控制
TOCTitle: 委派 Lync Server 2013 的管理控制
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520951(v=OCS.15)
ms:contentKeyID: 49312020
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 委派 Lync Server 2013 的管理控制

 

_**上一次修改主题：** 2013-02-22_

在 Lync Server 2013 中，使用新的基于角色的访问控制 (RBAC) 功能可将管理任务委派给用户。安装 Lync Server 时，会为您创建若干 RBAC 角色。这些角色对应于 Active Directory 域服务 中的通用安全组。例如，RBAC 角色 CsHelpDesk 对应于 Active Directory 域服务的“用户”容器中找到的 CsHelpDesk 组。此外，每个 RBAC 角色都与一组 Lync ServerWindows PowerShell cmdlet 关联。这些 cmdlet 代表已分配指定 RBAC 角色的用户可执行的任务。例如，CsHelpDesk 角色已分配 Lock-CsClientPin 和 UnlockCsClientPin cmdlet。这意味着已分配 CsHelpDesk 角色的用户可以锁定和解锁用户 PIN 号码。但是，CsHelpDesk 角色尚未分配 New-CsVoicePolicy cmdlet。这意味着已分配 CsHelpDesk 角色的用户不能创建新语音策略。

## 查看有关 RBAC 角色的信息

通过在 Lync Server 命令行管理程序中运行以下命令，可以检索有关 RBAC 角色的基本信息：

    Get-CsAdminRole

请记住，RBAC 角色（例如，CsVoiceAdministrator）的标识可直接映射到在 Active Directory 域服务的“用户”容器中找到的安全组。

要查看已分配给某个角色的 cmdlet 列表，请使用类似如下的命令：

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

## 将 RBAC 角色分配给用户

为了将 RBAC 角色分配给用户，必须将该用户添加到相应的 Active Directory 安全组。例如，要将 CsLocationAdministrator 角色分配给用户，必须将该用户添加到 CsLocationAdministrator 组。可通过执行以下过程完成此操作：

**将用户分配给安全组**

1.  使用具有修改 Active Directory 组成员身份权限的帐户，登录到已安装“Active Directory 用户和计算机”的计算机。

2.  依次单击“开始”、“所有程序”、“管理工具”，然后单击“Active Directory 用户和计算机”。

3.  在“Active Directory 用户和计算机”中，展开域名并单击“用户”容器。

4.  右键单击安全组“CsLocationAdministrator”，然后单击“属性”。

5.  在“属性”对话框的“成员”选项卡上，单击“添加”。

6.  在“选择用户、计算机、联系人或组”对话框的“输入要选择的对象名称”框中，键入要添加到组的用户的用户名或显示名称（例如， **Ken Myer** ），然后单击“确定”。

7.  在“属性”对话框中，单击“确定”。

若要验证是否分配了 RBAC 角色，请使用 [Get-CsAdminRoleAssignment](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet，向此 cmdlet 传递用户的 SamAccountName（Active Directory 登录名）。例如，在 Lync Server 命令行管理程序中运行以下命令：

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

