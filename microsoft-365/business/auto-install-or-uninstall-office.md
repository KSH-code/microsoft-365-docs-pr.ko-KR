---
title: Windows 10 장치에서 Office를 자동으로 설치 또는 제거
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Microsoft 365 비즈니스 관리 센터에서 Windows 10 장치에 Office를 설치 하거나 제거 합니다. '
ms.openlocfilehash: d82ab8292211d1adacba732922bf693dd2157ad6
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287538"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="e9925-103">Windows 10 장치에서 Office를 자동으로 설치 또는 제거</span><span class="sxs-lookup"><span data-stu-id="e9925-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="e9925-104">[![레이블-관리 센터가 변경 중 이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="e9925-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="e9925-105">Microsoft 365 Business 관리 센터에서 빠르고 쉽게 Windows 10 PC에 Office를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9925-105">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="e9925-106">이전에 설치한 Office 앱에서의 작동 방식을 알아보려면 시작하기 전에 [Office 클라이언트 설치 준비](prepare-for-office-client-deployment.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e9925-106">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="e9925-107">Office 배포 관리</span><span class="sxs-lookup"><span data-stu-id="e9925-107">Manage Office deployments</span></span>

1. <span data-ttu-id="e9925-108">전역 관리자 자격 증명을 사용하여 [관리 센터](https://aka.ms/bcsportal)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e9925-108">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="e9925-109">**장치** 카드에서 **Office 배포 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9925-109">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="e9925-110">**장치 작업** 카드가 표시 되지 않으면 관리 센터 **홈** 페이지에서 **추가** (+)를 클릭 하 여 관리자 홈에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9925-110">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="e9925-112">**Office 배포 관리** 창이 열리면 **그룹 추가**를 선택하여 사용할 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9925-112">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="e9925-113">그룹 또는 사용할 그룹을 추가한 후 **배포 작업** 드롭다운 목록에서 **가능한 한 빨리 Office 설치** 또는 **Office 제거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9925-113">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="e9925-115">Choose **Next** \> review the settings and then choose **Confirm**.</span><span class="sxs-lookup"><span data-stu-id="e9925-115">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="e9925-116">그룹 또는 사용한 그룹에서 지정된 사용자가 소유한 장치에서 32비트 Office가 자동으로 설치 또는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9925-116">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="e9925-117">Office 설치를 위해 선택된 컴퓨터의 작업 관리자를 열고 Microsoft Office 간편 실행 프로세스를 찾아 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9925-117">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


