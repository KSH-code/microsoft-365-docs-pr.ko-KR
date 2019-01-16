---
title: Windows 10 PC에서 앱 보호 설정 유효성 검사
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Windows 10 장치에서 Microsoft 365 비즈니스 응용 프로그램 보호 설정의 유효성을 검사 하는 방법에 알아봅니다.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869886"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="fe0cc-103">Windows 10 Pc에서 장치 보호 설정의 유효성을 검사합니다</span><span class="sxs-lookup"><span data-stu-id="fe0cc-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="fe0cc-104">Windows 10 장치 정책 설정 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="fe0cc-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="fe0cc-p101">[장치 정책 설정](protection-settings-for-windows-10-pcs.md)후 사용자의 장치에 영향을 정책에 대 한 몇 시간이 걸릴 수 있습니다. 사용자의 장치에서 다양 한 Windows 설정 화면에서 조회 하 여 정책 효과 수행한 되었는지 확인할 수 있습니다. 사용자가 자신의 Windows 10 장치에서 Windows Update 및 Windows Defender 바이러스 검사 설정을 수정할 수 없습니다, 때문에 이러한 옵션을 많이 회색으로 표시 될 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-p101">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices. You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices. Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="fe0cc-108">**설정** 으로 이동 \> **업데이트 &amp; 보안** \> **Windows Update** \> **옵션을 다시 시작** 하 고 모든 설정을 회색 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![모든 다시 시작 옵션은 회색으로 표시 합니다.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="fe0cc-110">**설정** 으로 이동 \> **업데이트 &amp; 보안** \> **Windows Update** \> **고급 옵션을** 하 고 모든 설정을 회색 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![Windows 고급 업데이트 옵션은 모든 회색으로 표시 합니다.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="fe0cc-112">**설정** 으로 이동 \> **업데이트 &amp; 보안** \> **Windows Update** \> **고급 옵션을** \> **업데이트 배달 되는 방법을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="fe0cc-113">모든 옵션이 회색으로 표시 되 고 일부 설정은 모두 숨겨져 있거나 조직에서 관리 하는 (빨간색)으로 메시지를 볼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![업데이트 배달 되는 방법을 선택 설정을 모두 숨겨져 있거나 조직에서 관리 하는 페이지를 나타냅니다.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="fe0cc-115">Windows Defender 보안 센터를 열려면 **설정** 으로 이동 \> **업데이트 &amp; 보안** \> **Windows Defender** \> **열기 Windows Defender 보안 센터** 를 클릭 \> **바이러스 &amp; 스레드 보호** \> **바이러스 &amp; 보호 설정을 위협**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="fe0cc-116">모든 옵션은 회색 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-116">Verify that all options are greyed out.</span></span> 
    
    ![바이러스 및 위협 보호 설정은 회색으로 표시 됩니다.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="fe0cc-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fe0cc-118">Related Topics</span></span>

[<span data-ttu-id="fe0cc-119">Microsoft 365 Business 문서 및 리소스</span><span class="sxs-lookup"><span data-stu-id="fe0cc-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="fe0cc-120">Microsoft 365 Business 시작</span><span class="sxs-lookup"><span data-stu-id="fe0cc-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="fe0cc-121">Microsoft 365 Business 관리</span><span class="sxs-lookup"><span data-stu-id="fe0cc-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="fe0cc-122">Windows 10 PC용 장치 구성 설정</span><span class="sxs-lookup"><span data-stu-id="fe0cc-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

