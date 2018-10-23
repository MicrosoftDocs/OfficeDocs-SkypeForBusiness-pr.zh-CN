---
title: Lync Server 2013：向 Active Directory 中添加 Survivable Branch Appliance
TOCTitle: 向 Active Directory 中添加 Survivable Branch Appliance
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425906(v=OCS.15)
ms:contentKeyID: 49312596
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中向 Active Directory 中添加 Survivable Branch Appliance

 

_**上一次修改主题：** 2012-09-23_

如果计划部署 Survivable Branch Appliance，必须将 Survivable Branch Appliance 添加到 Active Directory 域服务。请在中央站点执行此过程。

> [!IMPORTANT]  
> 仅当部署 Survivable Branch Appliance 时，才需执行此过程。如果要部署 Survivable Branch Server，请不要执行此过程。


## 将 Survivable Branch Appliance 添加到 Active Directory 域服务

1.  以 Enterprise Admins 组成员的身份登录到成员服务器。

2.  依次单击“开始”、“管理工具”、“Active Directory 用户和计算机”。

3.  在“操作”菜单上，单击“新建”，然后单击“计算机”。

4.  在“新建对象 - 计算机”对话框中，键入 Survivable Branch Appliance 计算机对象的名称（例如，BranchOffice1），然后单击“更改”。

5.  在“选择用户或组”对话框中，添加 RTCUniversalSBATechnicians 组，然后单击“确定”。
    
    > [!NOTE]  
    > 分支站点中 RTCUniversalSBATechnicians 组的成员稍后会将此设备添加到域。
    


6.  单击“确定”保存 Survivable Branch Appliance 计算机对象。

7.  单击“开始”，再单击“管理工具”，然后单击“ADSI Edit”。

8.  在“ADSI Edit”中，右键单击之前步骤中创建的计算机对象，然后单击“属性”。

9.  在属性列表中，单击“servicePrincipalName”，然后单击“编辑”。

10. 在“要添加的值”字段中，键入 HOST/\<SBA FQDN\>，其中 \<SBA FQDN\> 是您的 Survivable Branch Appliance 的完全限定的域名 (FQDN)。例如，键入 **HOST/BranchOffice1.contoso.com** 。

11. 单击“确定”保存“servicePrincipalName”属性设置，然后单击“确定”保存计算机对象属性。

12. 在“Active Directory 用户和计算机”中，右键单击“用户”，再单击“新建”，然后单击“用户”。

13. 在向导中输入信息，为 Survivable Branch Appliance 技术人员创建域用户帐户。

14. 在“Active Directory 用户和计算机”中，单击“用户”，右键单击用户对象，然后单击“添加到组”。

15. 在“输入要选择的对象名称”中，键入 **RTCUniversalSBATechnicians** ，然后单击“确定”。

16. 为每个分支站点技术人员重复步骤 12 至 15。

**下一步**：[在 Lync Server 2013 中向拓扑添加分支站点](lync-server-2013-add-branch-sites-to-your-topology.md)

