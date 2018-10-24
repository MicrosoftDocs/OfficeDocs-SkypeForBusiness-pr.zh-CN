---
title: Lync Server 2013：授予组织单位权限
TOCTitle: 授予组织单位权限
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398763(v=OCS.15)
ms:contentKeyID: 49313649
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中授予组织单位权限

 

_**上一次修改主题：** 2012-05-14_

可以使用 **Grant-CsOuPermission** cmdlet 向指定组织单位 (OU) 中的对象授予权限，以便林准备过程所创建的 RTC 通用组的成员无需成为 Domain Admins 组的成员即可对其进行访问。向指定 OU 添加的权限与在域准备过程中使用 **Enable-CsAdDomain** cmdlet 向计算机和用户容器添加的权限相同。

使用 **Test-CsOuPermission** cmdlet 验证您使用 **Grant-CsOuPermission** cmdlet 设置的权限。

可以使用 **Revoke-CsOuPermission** cmdlet 删除您使用 **Grant-CsOuPermission** cmdlet 授予的权限。

## 授予 OU 权限

1.  登录到要授予 OU 权限的域中运行 Lync Server 2013 的计算机。如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

## 验证 OU 权限

1.  登录到要验证 OU 权限的域中运行 Lync Server 2013 的计算机，这些权限是使用 **Grant-CsOuPermission** cmdlet 授予的。如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

## 吊销 OU 权限

1.  登录到要吊销 OU 权限的域中运行 Lync Server 2013 的计算机，这些权限是使用 **Grant-CsOuPermission** cmdlet 授予的。如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

