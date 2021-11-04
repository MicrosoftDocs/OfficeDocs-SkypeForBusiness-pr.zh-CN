---
title: Move File Store Data to a New File Store in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 如果需要删除当前充当 Skype for Business Server 2015 部署的文件存储的文件服务器，或者需要进行其他会使当前文件存储不可用的更改，则首先需要创建新的共享。 然后，您需要执行以下步骤：
ms.openlocfilehash: 73e66930f4c47ead3df01e04d30930b0257204e2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778372"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Move File Store Data to a New File Store in Skype for Business Server 2015

如果需要删除当前充当 Skype for Business Server 2015 部署的文件存储的文件服务器，或者需要进行其他会使当前文件存储不可用的更改，则首先需要创建新的共享。 然后，您需要执行以下步骤：

1. 关闭Skype for Business Server文件存储的 2015 服务。

2. 在拓扑生成器中定义文件存储并发布更改，使新文件存储可供部署使用。

3. 将数据移动到新文件存储。

4. 重新启动服务器或服务。

5. （可选）删除旧文件共享和文件文件夹。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>将文件存储数据从一个文件存储移动到新文件存储

1. 以 RTCUniversersalServerAdmins 或 CsServerAdministrator 组（其中安装了 Skype for Business Server 2015 管理工具）的成员登录到计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。

4. 对于使用计划删除的文件存储的每个控制器池、控制器、Standard Edition 服务器和前端池，选择服务器或池，单击"操作"，然后单击"停止 **所有服务"。** 

5. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

6. 启动拓扑生成器：单击"开始"，单击"所有程序"，Skype for Business Server **2015"，** 然后单击"Skype for Business Server **2015Topology Builder"。**

7. 选择使用文件存储的服务器或池，然后执行以下操作：

8. 右键单击服务器或池，然后单击"编辑 **属性"。**

9. 在 **"编辑属性"** 中的 **"关联"下的**"**文件存储"下**，单击"**新建"。**

10. 在 **"定义新文件** 存储"的"文件服务器 **FQDN"** 下，键入 (FQDN) 的完全限定域名。 在 **"文件共享**"下，键入新文件共享的文件夹名称，然后单击"确定 **"。**

     > [!IMPORTANT]
     > 此步骤定义用于拓扑生成器的新文件存储。 只需定义一次，而不是为每个服务器定义一次。 在发布拓扑之前，您必须在定义的文件服务器上创建定义的文件存储。 有关详细信息，请参阅[Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14))。

11. 对于使用文件存储的每个服务器或池，执行以下操作：

12. 右键单击服务器或池，然后单击"编辑 **属性"。**

13. 在 **"编辑属性**"中的 **"关联"下的**"**文件** 存储"中，选择新的文件共享，然后单击"确定 **"。**

14. 发布拓扑，检查复制状态，然后根据需要Skype for Business Server部署向导。 有关详细信息，请参阅[Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14))。

15. 启动命令提示符：单击"开始 **"，** 单击 **"运行**"，然后键入cmd.exe。

16. 在命令行中键入：

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S 开关复制文件、目录和子目录。 /XF 开关跳过名为 Meeting.Active 的所有文件。 带有 /MT 开关的 robocopy.exe 的当前版本通过使用多个线程大大提高了复制速度。 对于 /LOG 开关，请使用目录路径日志文件名称，格式为 C:\Logfiles\log.txt。 此开关在日志文件位置创建一系列操作。

17. 数据副本完成后，在 Lync Server 控制面板中，单击"拓扑 **"，** 然后单击"状态 **"。**

18. 对于停止服务的每个服务器或池，选择服务器或池，单击"**操作**"，然后单击"**启动所有服务"。**

19. 从拓扑中删除旧文件存储，然后发布拓扑。 有关详细信息，请参阅[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))。

20. （可选）以本地 Administrators 组或 Domain Admins 组的成员身份登录到包含您刚删除的文件存储的计算机，然后删除旧文件共享和目录。

## <a name="see-also"></a>另请参阅

[将服务器重新分配给另一个文件存储](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[删除文件存储](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))