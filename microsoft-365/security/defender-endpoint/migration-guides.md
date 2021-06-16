---
title: 끝점용 Microsoft Defender로 전환하기 위한 마이그레이션 가이드
description: 비보안 Defender 솔루션에서 끝점용 Microsoft Defender로 Microsoft 365 방법을 알아보십시오.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.custom: migrationguides
ms.reviewer: chriggs, depicker, yongrhee
f1.keywords: NOCSH
ms.date: 06/14/2021
ms.technology: mde
ms.openlocfilehash: 4d10de35358d528f004ee11e931fc6f41ce20482
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930502"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint-and-microsoft-defender-antivirus"></a><span data-ttu-id="d0b11-103">Endpoint 및 2013용 Microsoft Defender로 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="d0b11-103">Make the switch to Microsoft Defender for Endpoint and Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d0b11-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d0b11-104">**Applies to:**</span></span>
- [<span data-ttu-id="d0b11-105">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d0b11-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d0b11-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0b11-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d0b11-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d0b11-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d0b11-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b11-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="d0b11-109">마이그레이션 가이드</span><span class="sxs-lookup"><span data-stu-id="d0b11-109">Migration guides</span></span>

<span data-ttu-id="d0b11-110">비영리 Microsoft 365 Defender 솔루션에서 끝점용 Microsoft Defender로 전환하는 Microsoft Defender 바이러스 백신 마이그레이션 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b11-110">If you're considering switching from a non-Microsoft 365 Defender solution to Microsoft Defender for Endpoint with Microsoft Defender Antivirus, check out our migration guidance.</span></span> <span data-ttu-id="d0b11-111">배포 프로세스에서 가장 적합한 시나리오를 선택하고 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b11-111">Select the scenario that best represents where you are in your deployment process, and see the guidance.</span></span>

|<span data-ttu-id="d0b11-112">시나리오</span><span class="sxs-lookup"><span data-stu-id="d0b11-112">Scenario</span></span> |<span data-ttu-id="d0b11-113">지침</span><span class="sxs-lookup"><span data-stu-id="d0b11-113">Guidance</span></span> |
|:--|:--|
|<span data-ttu-id="d0b11-114">아직 끝점 보호 솔루션이 없는 경우 끝점용 Microsoft Defender가 어떻게 작동하고 & Microsoft Defender 바이러스 백신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b11-114">You do not have an endpoint protection solution yet, and you want to know more about how Microsoft Defender for Endpoint & Microsoft Defender Antivirus work.</span></span>  |[<span data-ttu-id="d0b11-115">끝점용 Microsoft Defender 평가 랩</span><span class="sxs-lookup"><span data-stu-id="d0b11-115">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
|<span data-ttu-id="d0b11-116">끝점용 Microsoft Defender & Microsoft Defender 바이러스 백신 설정하고 구성하는 데 도움이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b11-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span></span>  |[<span data-ttu-id="d0b11-117">끝점용 Microsoft Defender 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="d0b11-117">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
|<span data-ttu-id="d0b11-118">Microsoft가 아닌 끝점 보호 솔루션에서 끝점용 Microsoft Defender 솔루션으로 마이그레이션할 & Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="d0b11-118">You're planning to migrate from a non-Microsoft endpoint protection solution to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="d0b11-119">끝점용 Microsoft Defender로 전환</span><span class="sxs-lookup"><span data-stu-id="d0b11-119">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
|<span data-ttu-id="d0b11-120">Microsoft Defender for Endpoint & Microsoft Defender 바이러스 백신 마이그레이션한 후 추가 기능 구성 또는 보안 설정 미세 조정과 같은 다음 단계에 대한 도움이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b11-120">You've migrated to Microsoft Defender for Endpoint & Microsoft Defender Antivirus, and you need help with next steps, such as configuring additional features or fine-tuning your security settings.</span></span> | [<span data-ttu-id="d0b11-121">끝점용 Microsoft Defender 관리, 마이그레이션 후</span><span class="sxs-lookup"><span data-stu-id="d0b11-121">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="do-you-have-feedback-for-us"></a><span data-ttu-id="d0b11-122">피드백이 있나요?</span><span class="sxs-lookup"><span data-stu-id="d0b11-122">Do you have feedback for us?</span></span>

<span data-ttu-id="d0b11-123">의견을 전달해주세요!</span><span class="sxs-lookup"><span data-stu-id="d0b11-123">Let us know what you think!</span></span> <span data-ttu-id="d0b11-124">페이지 아래쪽에 피드백을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b11-124">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="d0b11-125">계속해서 개선되고 마이그레이션 지침에 추가될 때 피드백을 고려할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b11-125">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0b11-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0b11-126">See also</span></span>

- [<span data-ttu-id="d0b11-127">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d0b11-127">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="d0b11-128">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d0b11-128">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="d0b11-129">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0b11-129">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
