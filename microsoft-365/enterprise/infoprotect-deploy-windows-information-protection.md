---
title: '4단계: WIP(Windows Information Protection) 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365에서 WIP(Windows Information Protection) 이해 및 배포
ms.openlocfilehash: e32b09c20e86ff927748f7aedd8b8d769e07916e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073568"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="eb856-103">4단계: WIP(Windows Information Protection) 구성</span><span class="sxs-lookup"><span data-stu-id="eb856-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="eb856-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="eb856-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="eb856-105">더 많은 개인 장치를 작업에 사용할 수 있으므로, 개인 조직 데이터를 누출할 수 있는 앱 및 장치의 위험이 높아졌습니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-105">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="eb856-106">예를 들어, 직원이 실수로 미래 제품에 대한 마케팅 계획의 사진을 소셜 미디어에 전송하거나 매우 중요한 정보를 공개 클라우드 스토리지에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-106">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="eb856-107">WIP(Windows Information Protection)를 사용하여 Windows 10 장치에서 이러한 유형의 데이터 누출을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-107">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="eb856-108">자세한 내용은 [WIP를 사용한 엔터프라이즈 데이터 보호](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb856-108">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="eb856-109">Microsoft 365 Enterprise에서, WIP는 구독 시 Enterprise Mobility + Security(EMS)에 포함된 Windows 10 Enterprise 및 Microsoft Intune의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-109">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with Enterprise Mobility + Security (EMS) in your subscription.</span></span> 

<span data-ttu-id="eb856-110">Microsoft 365 Enterprise와 함께 조직에 WIP를 배포하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-110">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="eb856-111">Intune에 Windows 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-111">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="eb856-112">[5단계: 모바일 장치 관리](mobility-infrastructure.md)에서 이 작업을 했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-112">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="eb856-113">[WIP용 Intune 정책](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-113">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="eb856-114">제한된 앱 목록을 작성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-114">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="eb856-115">WIP 보호 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-115">Choose your WIP protection level.</span></span>

<span data-ttu-id="eb856-116">[System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm)에 WIP를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-116">You can also use WIP with [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="eb856-117">자세한 내용은 [WIP 모범 사례]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb856-117">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="eb856-118">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step4)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="eb856-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="eb856-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="eb856-119">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="eb856-120">Office 365 데이터 손실 방지 구성</span><span class="sxs-lookup"><span data-stu-id="eb856-120">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


