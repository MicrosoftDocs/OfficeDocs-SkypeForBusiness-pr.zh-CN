---
title: 将多个用户移动到试点池
TOCTitle: 将多个用户移动到试点池
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205096(v=OCS.15)
ms:contentKeyID: 49313585
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将多个用户移动到试点池

 

_**上一次修改主题：** 2012-10-02_

您可以使用 Lync Server 2013 控制面板 或 Lync Server 2013 命令行管理程序 将多个用户从 Lync Server 2010 池移动到 Lync Server 2013 试点池。

## 使用 Lync Server 2013 控制面板移动多个用户

1.  打开“Lync Server 控制面板”。

2.  依次单击“用户”、“搜索”和“查找”。

3.  选择要移至 Lync Server 2013 池的两个用户。在此示例中，我们将移动用户 Chen Yang 和 Claus Hansen。
    
    ![将用户移到特定的注册器池](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "将用户移到特定的注册器池")  

4.  从“操作”菜单中，选择“将所选用户移动到池”。

5.  从下拉列表中，选择 Lync Server 2013 池。

6.  单击“操作”，然后单击“将所选用户移动到池”。单击“确定”。
    
    ![移动用户 -“目标注册器池”对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移动用户 -“目标注册器池”对话框")  

7.  确认该用户的“注册器池”列现在包含 Lync Server 2013 池，这表明已成功移动该用户。

## 使用 Lync Server 2013 命令行管理程序 移动多个用户

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中，键入以下命令，并将 **User1** 和 **User2** 替换为要移动的具体用户名，将 **pool\_FQDN** 替换为目标池的名称。在本例中，我们将移动用户 Hao Chen 和 Katie Jordan。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell Get-CsUser cmdlet 示例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-CsUser cmdlet 示例")  

3.  在命令行中键入：
    
        Get-CsUser -Identity "User1"

4.  **Registrar Pool** 标识现在应该指向在上一步中指定为 **pool\_FQDN** 的池。存在该标识即可确认已成功移动用户。重复此步骤以确认 **User2** 已移动。
    
    ![PowerShell Get-UsUser -Identity cmdlet 的输出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser -Identity  cmdlet 的输出")  

## 使用 Lync Server 2013 命令行管理程序同时移动所有用户

在本例中，所有用户均已返回到 Lync Server 2010 池 (pool01.contoso.net)。通过使用 Lync Server 2013 命令行管理程序，我们将所有用户同时移动到 Lync Server 2013 池 (pool02.contoso.net)。

1.  打开 **Lync Server 2013 命令行管理程序**。

2.  在命令行中键入：
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell cmdlet 和命令行管理程序中的结果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet 和命令行管理程序中的结果")  

3.  接下来，为试点用户之一运行 **Get-CsUser**。
    
        Get-CsUser -Identity "Hao Chen"

4.  每个用户的 **Registrar Pool** 标识现在指向在上一步中指定为“pool\_FQDN”的池。存在该标识即可确认已成功移动用户。

5.  此外，我们可以在 Lync Server 2013 控制面板中查看用户列表，并验证 Registrar Pool 值现在是否指向 Lync Server 2013 池。
    
    ![Lync Server 2013 控制面板用户列表](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制面板用户列表")

