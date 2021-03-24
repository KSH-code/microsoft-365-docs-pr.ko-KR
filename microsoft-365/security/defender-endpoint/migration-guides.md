---
title: 끝점용 Microsoft Defender로 전환하기 위한 마이그레이션 가이드
description: Microsoft가 아닌 위협 방지 솔루션에서 끝점용 Microsoft Defender로 전환하는 방법을 알아보십시오.
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
ms.date: 09/24/2020
ms.technology: mde
ms.openlocfilehash: 72a4385fb65c02d5b9e8d1b51bc376e31cb13db3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069471"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint-and-microsoft-defender-antivirus"></a><span data-ttu-id="37dec-103">Endpoint용 Microsoft Defender 및 Microsoft Defender 바이러스 백신으로 전환</span><span class="sxs-lookup"><span data-stu-id="37dec-103">Make the switch to Microsoft Defender for Endpoint and Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37dec-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="37dec-104">**Applies to:**</span></span>
- [<span data-ttu-id="37dec-105">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37dec-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="37dec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37dec-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="37dec-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="37dec-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="37dec-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="37dec-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="37dec-109">마이그레이션 가이드</span><span class="sxs-lookup"><span data-stu-id="37dec-109">Migration guides</span></span>

<span data-ttu-id="37dec-110">Microsoft Defender 바이러스 백신을 사용하여 Microsoft가 아닌 위협 방지 솔루션에서 끝점용 Microsoft Defender로 전환하려는 경우 마이그레이션 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37dec-110">If you're considering switching from a non-Microsoft threat protection solution to Microsoft Defender for Endpoint with Microsoft Defender Antivirus, check out our migration guidance.</span></span> <span data-ttu-id="37dec-111">배포 프로세스에서 가장 적합한 시나리오를 선택하고 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37dec-111">Select the scenario that best represents where you are in your deployment process, and see the guidance.</span></span>

|<span data-ttu-id="37dec-112">시나리오</span><span class="sxs-lookup"><span data-stu-id="37dec-112">Scenario</span></span> |<span data-ttu-id="37dec-113">지침</span><span class="sxs-lookup"><span data-stu-id="37dec-113">Guidance</span></span> |
|:--|:--|
|<span data-ttu-id="37dec-114">아직 끝점 보호 솔루션이 없는 경우 Microsoft Defender 바이러스 백신이 어떻게 작동하고, Endpoint용 Microsoft Defender & 알고 싶을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37dec-114">You do not have an endpoint protection solution yet, and you want to know more about how Microsoft Defender for Endpoint & Microsoft Defender Antivirus work.</span></span>  |[<span data-ttu-id="37dec-115">끝점용 Microsoft Defender 평가 랩</span><span class="sxs-lookup"><span data-stu-id="37dec-115">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
|<span data-ttu-id="37dec-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span><span class="sxs-lookup"><span data-stu-id="37dec-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span></span>  |[<span data-ttu-id="37dec-117">끝점용 Microsoft Defender 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="37dec-117">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
|<span data-ttu-id="37dec-118">McAfee Endpoint Security(McAfee)에서 Microsoft Defender 바이러스 백신을 사용하여 끝점용 Microsoft Defender로 & 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="37dec-118">You're planning to migrate from McAfee Endpoint Security (McAfee) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="37dec-119">McAfee에서 끝점용 Microsoft Defender로 전환</span><span class="sxs-lookup"><span data-stu-id="37dec-119">Switch from McAfee to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-migration.md) |
|<span data-ttu-id="37dec-120">Symantec Endpoint Protection(Symantec)에서 Microsoft Defender 바이러스 백신을 사용하여 끝점용 Microsoft Defender로 & 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="37dec-120">You're planning to migrate from Symantec Endpoint Protection (Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="37dec-121">Symantec에서 끝점용 Microsoft Defender로 전환</span><span class="sxs-lookup"><span data-stu-id="37dec-121">Switch from Symantec to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-migration.md) |
|<span data-ttu-id="37dec-122">Microsoft Defender 바이러스 백신을 사용하여 Microsoft가 아닌 다른 끝점 보호 솔루션(McAfee 또는 Symantec 외)에서 Endpoint용 Microsoft Defender로 & 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="37dec-122">You're planning to migrate from a non-Microsoft endpoint protection solution (other than McAfee or Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="37dec-123">끝점용 Microsoft Defender로 전환</span><span class="sxs-lookup"><span data-stu-id="37dec-123">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
|<span data-ttu-id="37dec-124">Microsoft Defender 바이러스 백신용 Microsoft Defender로 & 추가 기능을 구성하거나 보안 설정을 미세 조정하는 등 다음 단계에 대한 도움이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37dec-124">You've migrated to Microsoft Defender for Endpoint & Microsoft Defender Antivirus, and you need help with next steps, such as configuring additional features or fine-tuning your security settings.</span></span> | [<span data-ttu-id="37dec-125">끝점용 Microsoft Defender 관리, 마이그레이션 후</span><span class="sxs-lookup"><span data-stu-id="37dec-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="got-feedback"></a><span data-ttu-id="37dec-126">피드백이 있나요?</span><span class="sxs-lookup"><span data-stu-id="37dec-126">Got feedback?</span></span>

<span data-ttu-id="37dec-127">의견을 전달해주세요!</span><span class="sxs-lookup"><span data-stu-id="37dec-127">Let us know what you think!</span></span> <span data-ttu-id="37dec-128">페이지 아래쪽에 피드백을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="37dec-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="37dec-129">계속해서 개선되고 마이그레이션 지침에 추가될 때 피드백을 고려할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37dec-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="37dec-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37dec-130">See also</span></span>

- [<span data-ttu-id="37dec-131">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37dec-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
- [<span data-ttu-id="37dec-132">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37dec-132">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [<span data-ttu-id="37dec-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37dec-133">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection?) 
