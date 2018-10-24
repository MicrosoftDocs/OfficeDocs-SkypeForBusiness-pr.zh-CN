---
title: 将单个用户移动到试点池
TOCTitle: 将单个用户移动到试点池
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49888484
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将单个用户移动到试点池

 

_**上一次修改主题：** 2012-09-28_

您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序将用户从 Office Communications Server 2007 R2 池移动到 Lync Server 2013 试点池。在下面的示例中，在注册器池列中， **\<Office Communications Server\>** 是 Office Communications Server 2007 R2 池，所有这六个用户都将连接到此池。按照以下过程，使用 Lync Server 2013 控制面板和 Lync Server 命令行管理程序将用户移动到 Lync Server 2013 池。

![在 Lync Server 控制面板中搜索 OCS 用户](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "在 Lync Server 控制面板中搜索 OCS 用户")

## 使用 Lync Server 2013 控制面板 移动用户

1.  使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。

2.  打开 Lync Server 控制面板。

3.  单击“用户”。

4.  从“用户搜索”选项卡中，单击“搜索”按钮。

5.  接下来，单击“添加筛选器”。

6.  创建一个筛选器，其中的 **Office Communications Server 用户**等于 **True**。

7.  单击“查找”搜索旧 Office Communications Server 2007 R2 用户。
    
    ![在 Lync Server 控制面板中搜索 OCS 用户](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "在 Lync Server 控制面板中搜索 OCS 用户")  

8.  选择要移至 Lync Server 2013 池的用户。在此示例中，将移动用户 Sara Davis。

9.  在“操作”菜单中，选择“将所选用户移动到池”。

10. 从下拉列表中，选择 Lync Server 2013 池。

11. 单击“操作”，然后单击“将所选用户移动到池”。单击“确定”。
    
    ![在“移动用户”对话框中设置目标池](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "在“移动用户”对话框中设置目标池")  

12. 确认该用户的“注册器池”列现在包含 Lync Server 2013 池，这表明已成功移动该用户

## 使用 Lync Server 2013 命令行管理程序移动用户

1.  打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  下一步，在命令行中键入：
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool** 标识现在指向 Lync Server 2013 池。存在该标识即可确认已成功移动用户。
    
    ![使用 Identity 筛选器的 Get-CsUser cmdlet 的输出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "使用 Identity 筛选器的 Get-CsUser cmdlet 的输出")  
    
    > [!NOTE]
    > 有关 <strong>Get-CsUser</strong> cmdlet 的详细信息，请运行：<strong>Get-Help Get-CsUser –Detailed</strong>

