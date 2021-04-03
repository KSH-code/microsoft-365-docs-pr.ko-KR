---
title: Windows 10 PC에서 앱 보호 설정 유효성 검사
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 비즈니스용 Microsoft 365 앱 보호 설정이 사용자의 Windows 10 디바이스에 적용된 것을 확인하는 방법을 확인합니다.
ms.openlocfilehash: fcb463fd98f692f7d4802689e0c03fe4e3e648a1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579845"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="0bf6c-103">Windows 10 PC에서 장치 보호 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0bf6c-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="0bf6c-104">Windows 10 장치 정책이 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0bf6c-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="0bf6c-105">장치 정책을 [설정한](protection-settings-for-windows-10-pcs.md)후 정책이 사용자의 장치에 적용되는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf6c-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="0bf6c-106">사용자 장치에서 다양한 Windows 설정 화면을 확인하여 정책이 적용된 것으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf6c-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="0bf6c-107">사용자가 Windows 10 장치에서 Windows 업데이트 및 Windows Defender 바이러스 백신 설정을 수정할 수 없는 경우 많은 옵션이 회색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bf6c-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="0bf6c-108">설정 **업데이트** 보안 Windows 업데이트 다시 시작 옵션으로 이동하여 모든 설정이 \> **&amp;** \>  \>  회색으로 표시되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf6c-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![다시 시작 옵션은 모두 회색으로 표시됩니다.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="0bf6c-110">설정 업데이트 **보안** Windows 업데이트 고급 옵션으로 이동하여 모든 설정이 \> **&amp;** \>  \>  회색으로 표시되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf6c-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows 고급 업데이트 옵션은 모두 회색으로 표시됩니다.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="0bf6c-112">설정  업데이트 \> **보안 &amp;** \> **Windows 업데이트** \> **고급 옵션 업데이트** 제공 방법 \> **선택으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0bf6c-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="0bf6c-113">일부 설정이 조직에서 숨겨지거나 관리되고 모든 옵션이 회색으로 표시되고 메시지가 빨간색으로 표시될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf6c-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![업데이트 배달 방법 선택 페이지에는 조직에서 설정을 숨기거나 관리하는 설정이 표시됩니다.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="0bf6c-115">Windows Defender 보안 센터를 열려면 설정  업데이트 보안 Windows Defender 보안 센터 바이러스 스레드 보호 바이러스 위협 Windows Defender 설정을 \> **&amp;** \>  \>  \> **&amp;** \> **&amp; 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0bf6c-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="0bf6c-116">모든 옵션이 회색으로 표시 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0bf6c-116">Verify that all options are grayed out.</span></span> 
    
    ![바이러스 및 위협 방지 설정은 회색으로 표시됩니다.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="0bf6c-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0bf6c-118">Related Topics</span></span>

[<span data-ttu-id="0bf6c-119">비즈니스용 Microsoft 365 설명서 및 리소스</span><span class="sxs-lookup"><span data-stu-id="0bf6c-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="0bf6c-120">비즈니스용 Microsoft 365 시작</span><span class="sxs-lookup"><span data-stu-id="0bf6c-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="0bf6c-121">비즈니스용 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="0bf6c-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="0bf6c-122">Windows 10 PC용 장치 구성 설정</span><span class="sxs-lookup"><span data-stu-id="0bf6c-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
