---
title: 将单个用户移动到试点池
TOCTitle: 将单个用户移动到试点池
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205401(v=OCS.15)
ms:contentKeyID: 49314616
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将单个用户移动到试点池

 

_**上一次修改主题：** 2012-09-26_

可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序将用户从 Lync Server 2010 池移动到 Lync Server 2013 试点池。在“注册器池”列中，**pool01.contoso.net** 是 Lync Server 2010 池，所有这些六个用户都连接到此池。使用下列过程利用 Lync Server 2013 控制面板和 Lync Server 命令行管理程序将用户移动到 Lync Server 2013 池。

## 使用 Lync Server 2013 控制面板 移动用户

**Lync Server 2013 控制面板中的用户列表**

![Lync Server 控制面板 -“移动用户”对话框](images/JJ205401.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server 控制面板 -“移动用户”对话框")

1.  使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。

2.  打开“Lync Server 控制面板”。

3.  依次单击“用户”、“搜索”和“查找”。

4.  选择要移至 Lync Server 2013 池的用户。在此示例中，将移动用户 Sara Davis。

5.  在“操作”菜单中，选择“将所选用户移动到池”。

6.  从下拉列表中，选择 Lync Server 2013 池。

7.  单击“操作”，然后单击“将所选用户移动到池”。单击“确定”。
    
    ![移动用户 -“目标注册器池”对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移动用户 -“目标注册器池”对话框")  

8.  确认该用户的“注册器池”列现在包含 Lync Server 2013 池，这表明已成功移动该用户。

## 使用 Lync Server 2013 命令行管理程序移动用户

1.  打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  下一步，在命令行中键入：
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool** 标识现在指向 Lync Server 2013 池。存在该标识即可确认已成功移动用户。
    
    ![使用 Identity 筛选器的 Get-CsUser cmdlet 的输出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "使用 Identity 筛选器的 Get-CsUser cmdlet 的输出")  
    
    > [!NOTE]
    > 有关 <strong>Get-CsUser</strong> cmdlet 的详细信息，请运行：<strong>Get-Help Get-CsUser –Detailed</strong>

