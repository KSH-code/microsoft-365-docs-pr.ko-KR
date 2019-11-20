---
title: Windows 10 PC에서 앱 보호 설정 유효성 검사
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Windows 10 장치에서 Microsoft 365 Business 앱 보호 설정을 확인 하는 방법을 알아봅니다.
ms.openlocfilehash: b8793ab7f77bbc7f608f237e2455f6fd12c3bb26
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721803"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="ff55b-103">Windows 10 Pc에서 장치 보호 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ff55b-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="ff55b-104">Windows 10 장치 정책이 설정 되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ff55b-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="ff55b-105">[장치 정책을 설정한](protection-settings-for-windows-10-pcs.md)후에는 정책이 사용자 장치에 적용 되는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="ff55b-106">사용자 장치에서 다양 한 Windows 설정 화면을 살펴보면 정책이 적용 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="ff55b-107">사용자가 Windows 10 장치에서 Windows Update 및 Windows Defender 바이러스 백신 설정을 수정할 수 없으므로 많은 옵션이 흐리게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="ff55b-108">**설정** \> **업데이트 &amp; 보안** \> **Windows** 업데이트 \> **다시 시작 옵션** 으로 이동 하 여 모든 설정이 회색으로 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![모든 다시 시작 옵션이 회색으로 표시 됩니다.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="ff55b-110">**설정** \> **업데이트 &amp; 보안** \> **Windows** 업데이트 \> **고급 옵션** 으로 이동 하 여 모든 설정이 회색으로 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows 고급 업데이트 옵션은 모두 회색으로 표시 됩니다.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="ff55b-112">**설정** \> **업데이트 &amp; 보안** \> **Windows** 업데이트 \> **고급** 옵션 \> 으로 이동 **하 여 업데이트를 배달 하는 방법을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="ff55b-113">일부 설정이 조직에 의해 숨겨지거나 관리 되 고 모든 옵션이 회색으로 표시 되는 메시지 (빨간색)를 볼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![업데이트를 전달 하는 방법 선택 페이지 설정이 숨겨지거나 관리 됨에 따라 결정 됩니다.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="ff55b-115">Windows defender 보안 센터를 열려면 **설정** \> \*\* &amp; 업데이트 보안\*\* \> **windows defender** \> 를 클릭 하 여 **windows defender 보안 센터** \> **바이러스 &amp; 스레드 보호** \> **바이러스 &amp; 위협 방지 설정을**엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="ff55b-116">모든 옵션이 회색으로 표시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff55b-116">Verify that all options are grayed out.</span></span> 
    
    ![바이러스 및 위협 방지 설정이 회색으로 표시 됩니다.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="ff55b-118">관련 주제</span><span class="sxs-lookup"><span data-stu-id="ff55b-118">Related Topics</span></span>

[<span data-ttu-id="ff55b-119">Microsoft 365 Business 문서 및 리소스</span><span class="sxs-lookup"><span data-stu-id="ff55b-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="ff55b-120">Microsoft 365 Business 시작</span><span class="sxs-lookup"><span data-stu-id="ff55b-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="ff55b-121">Microsoft 365 Business 관리</span><span class="sxs-lookup"><span data-stu-id="ff55b-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="ff55b-122">Windows 10 PC용 장치 구성 설정</span><span class="sxs-lookup"><span data-stu-id="ff55b-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

