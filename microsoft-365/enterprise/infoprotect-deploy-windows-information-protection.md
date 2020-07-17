---
title: '4단계: WIP(Windows Information Protection) 구성'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365에서 WIP(Windows Information Protection) 이해 및 배포
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005725"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="7a139-103">4단계: WIP(Windows Information Protection) 구성</span><span class="sxs-lookup"><span data-stu-id="7a139-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="7a139-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7a139-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="7a139-106">더 많은 개인 장치를 작업에 사용할 수 있으므로, 개인 조직 데이터를 누출할 수 있는 앱 및 장치의 위험이 높아졌습니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="7a139-107">예를 들어, 직원이 실수로 미래 제품에 대한 마케팅 계획의 사진을 소셜 미디어에 전송하거나 매우 중요한 정보를 공개 클라우드 스토리지에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="7a139-108">WIP(Windows Information Protection)를 사용하여 Windows 10 장치에서 이러한 유형의 데이터 누출을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="7a139-109">자세한 내용은 [WIP를 사용한 엔터프라이즈 데이터 보호](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a139-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="7a139-110">Microsoft 365 Enterprise에서, WIP는 구독에 포함된 Windows 10 Enterprise 및 Microsoft Intune의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="7a139-111">Microsoft 365 Enterprise와 함께 조직에 WIP를 배포하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="7a139-112">Intune에 Windows 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="7a139-113">[5단계: 모바일 장치 관리](mobility-infrastructure.md)에서 이 작업을 했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>

2. <span data-ttu-id="7a139-114">[WIP용 Intune 정책](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>

   -    <span data-ttu-id="7a139-115">제한된 앱 목록을 작성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-115">Ensure that you have filled out your Protected apps list.</span></span>
  
   - <span data-ttu-id="7a139-116">WIP 보호 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="7a139-117">[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr)에서 WIP를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a139-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr).</span></span> 

<span data-ttu-id="7a139-118">자세한 내용은 [WIP 모범 사례]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a139-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="7a139-119">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step4)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7a139-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="7a139-120">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7a139-120">Next step</span></span>

|||
|:-------|:-----|
|![5단계](../media/stepnumbers/Step5.png)|[<span data-ttu-id="7a139-122">구성 데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="7a139-122">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


