---
title: Lync Server 2013：授予安装权限
TOCTitle: 授予安装权限
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398225(v=OCS.15)
ms:contentKeyID: 49312099
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中授予安装权限

 

_**上一次修改主题：** 2012-08-27_

您可使用 **Grant-CsSetupPermission** cmdlet 为指定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 组添加读取、写入、ReadSPN 和 WriteSPN 权限。之后，该 OU 中 RTCUniversalServerAdmins 组的成员无需成为 Domain Admins 组的成员即可在指定的域中安装运行 Lync Server 2013 的服务器。

使用 **Test-CsSetupPermission** cmdlet 验证您使用 **Grant-CsSetupPermission** cmdlet 设置的权限。

可以使用 **Revoke-CsSetupPermission** cmdlet 删除您使用 **Grant-CsSetupPermission** cmdlet 授予的权限。

## 授予安装权限

1.  登录到在要授予安装权限的域中运行 Lync Server 2013 的计算机。如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。
    
    如果不指定 Domain 参数，则默认值为本地域。

## 验证安装权限

1.  登录到在要验证使用 **Grant-CsSetupPermission** cmdlet 授予的安装权限的域中运行 Lync Server 2013 的计算机。如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。
    
    如果不指定 Domain 参数，则默认值为本地域。

## 撤消安装权限

1.  登录到在要撤消使用 **Grant-CsSetupPermission** cmdlet 授予的安装权限的域中运行 Lync Server 2013 的计算机。如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。
    
    如果不指定 Domain 参数，则默认值为本地域。

