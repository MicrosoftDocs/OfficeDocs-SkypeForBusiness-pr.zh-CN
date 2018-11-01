---
title: Lync Server 2013：安装 Lync Server 管理工具
TOCTitle: 安装 Lync Server 管理工具
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398665(v=OCS.15)
ms:contentKeyID: 49313466
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 Lync Server 2013 管理工具

 

_**上一次修改主题：** 2013-02-21_

本主题介绍如何安装部署和管理 Lync Server 2013 所需使用的管理工具。默认情况下，这些管理工具安装在运行 Lync Server 2013 的每台服务器上。此外，您可在其他计算机（如专用管理控制台）上安装这些管理工具。强烈建议您在位于将创建的 Lync Server 2013 部署所在的域或林中的计算机上安装这些管理工具，因为这样做可确保成功完成 Active Directory 域服务 准备步骤，从而使您能够稍后在该计算机上使用这些管理工具来发布拓扑。

在安装或使用 Lync Server 2013 管理工具之前，请务必查看基础结构、操作系统、软件和管理员权限要求。有关基础结构要求的详细信息，请参阅[Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。有关安装 Lync Server 2013 管理工具的操作系统和软件要求的详细信息，请参阅[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)、[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)和[Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。有关安装和使用这些工具所需的用户权限的详细信息，请参阅[Lync Server 2013 的安装和管理所需的管理员权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)。

> [!IMPORTANT]
> 如果组织要求您在系统驱动器之外的某个驱动器上定位 Internet Information Services (IIS) 和所有 Web Services，您可以在“安装”对话框中更改 Lync Server 文件的安装位置路径。如果您将安装文件（包括 OCSCore.msi）安装到此路径，则其余的 Lync Server 2013 文件也将部署到该驱动器。


## 安装 Lync Server 2013 管理工具

1.  以本地管理员身份登录（最低要求）要安装管理工具的计算机。如果您以标准用户身份登录 Windows Vista 或 Windows 7 操作系统，并且启用了用户帐户控制 (UAC)，则系统将提示您输入本地管理员或域等效用户的名称和密码。

2.  在计算机上找到安装媒体，然后双击 \\Setup\\amd64\\Setup.exe。

3.  如果提示您安装 Microsoft Visual C++ 2008 可发行软件包，请单击“是”。

4.  在“Microsoft Lync Server 2013 安装位置”页上，单击“确定”。如果要将文件安装至其他位置，请将此路径更改为相应的位置或驱动器。
    
    > [!IMPORTANT]
    > 如果组织要求您在系统驱动器之外的某个驱动器上定位 Internet Information Services (IIS) 和所有 Web 服务，您可以在“安装”对话框中更改 Lync Server 2013 文件的安装位置路径。如果您将安装文件（包括 OCSCore.msi）安装到此路径，则其余的 Lync Server 2013 文件也将部署到该驱动器。


5.  在“最终用户许可协议”页上，查看许可条款，单击“我接受”，然后单击“确定”。必须完成此步骤，才能继续安装。

6.  在“Microsoft Lync Server 2013 – 部署向导”页上，单击“安装管理员工具”。

7.  安装成功完成后，单击“退出”。

## 另请参阅

#### 任务

[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)  

#### 概念

[Lync Server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)

