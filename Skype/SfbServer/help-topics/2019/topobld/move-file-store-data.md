---
title: 移动文件存储数据移到新文件存储中的业务服务器 Skype
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 如果您需要删除目前充当业务服务器部署中，您 Skype 的文件存储的文件服务器，或如果您需要进行其他更改，使当前文件存储不可用，首先需要创建新的共享。 然后需要执行以下步骤：
ms.openlocfilehash: de76c0cbb3a6516ebd3769ba44733be5aa4485e6
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245878"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>移动文件存储数据移到新文件存储中的业务服务器 Skype

如果您需要删除目前充当业务服务器部署中，您 Skype 的文件存储的文件服务器，或如果您需要进行其他更改，使当前文件存储不可用，首先需要创建新的共享。 然后需要执行以下步骤：

1. 关闭使用计划删除的文件存储的业务 Server 服务的 Skype。

2. 拓扑生成器中定义的文件存储，然后发布更改，以使新文件存储供您的部署。

3. 将数据移动到新的文件存储。

4. 重新启动服务器或服务。

5. （可选）删除旧的文件共享和文件夹。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>将文件存储数据从一个文件存储移动到新文件存储

1. 安装 Business Server，管理工具的 Skype 以 RTCUniversersalServerAdmins 或 CsServerAdministrator 组的成员身份登录到计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。

4. 为每个控制器池、 控制器、 Standard Edition server 和使用计划删除的文件存储的前端池，选择服务器或池，单击**操作**，然后单击**停止所有服务**。

5. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

6. 启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server 拓扑生成器**。

7. 选择使用文件存储的服务器或池，然后执行以下操作：

1. 右键单击服务器或池，然后单击“**编辑属性**”。

2. 在“**编辑属性**”中的“**关联**”下的“**文件存储**”下面，单击“**新建**”。

3. 在“**定义新文件存储**”中的“**文件服务器 FQDN**”下，键入文件服务器的完全限定域名 (FQDN)。在“**文件共享**”下，键入新文件共享的文件夹名称，然后单击“**确定**”。

    > [!IMPORTANT]
    > 此步骤在拓扑生成器中定义为使用新文件存储。 只需定义一次，无需针对每台服务器定义。 发布拓扑之前，必须在定义的文件服务器上创建定义的文件共享。 有关详细信息，请参阅[定义前端的文件存储区](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)。

8. 对于每个使用文件存储的服务器或池，执行以下操作：

1. 右键单击服务器或池，然后单击“**编辑属性**”。

2. 在“**编辑属性**”中的“**关联**”下面的“**文件存储**”中，选择新的文件共享，然后单击“**确定**”。

9. 发布拓扑，检查复制状态，并根据需要业务 Server 部署向导运行 Skype。 有关详细信息，请参阅[Removing Lync Servers and 组件的常见过程](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)。

10. 启动命令提示符： 单击**开始**，单击**运行**，然后键入 cmd.exe。

11. 在命令行中键入：

  ```
  Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
  ```

    > [!TIP]
    > /S 开关复制文件、目录和子目录。 /XF 开关跳过名为 Meeting.Active 的所有文件。 带有 /MT 开关的 robocopy.exe 的当前版本通过使用多个线程大大提高了复制速度。 对于 /LOG 开关，使用 C:\Logfiles\log.txt 的窗体中的目录路径和日志文件名称。 该开关可在指定位置创建操作的日志文件。

12. 数据复制完成后，在 Lync Server Control Panel 后，单击**拓扑**，，然后单击**状态**。

13. 对于已停止服务的每个服务器或池，选择该服务器或池，单击“**操作**”，然后单击“**启动所有服务**”。

14. 从拓扑中删除旧文件存储，然后发布拓扑。 有关详细信息，请参阅[删除文件存储](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)。

15. （可选）以本地 Administrators 组或 Domain Admins 组的成员身份登录到包含你刚删除的文件存储的计算机，然后删除旧文件共享和目录。

## <a name="see-also"></a>另请参阅

[重新分配到不同的文件存储的服务器](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[删除文件存储](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)