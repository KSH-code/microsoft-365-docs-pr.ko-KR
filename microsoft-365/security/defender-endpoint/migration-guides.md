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
ms.openlocfilehash: a0b1f82ae26ba1103ed4cc7eb0be7e9c376b5f52
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933038"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="20c5d-103">끝점용 Microsoft Defender로 전환</span><span class="sxs-lookup"><span data-stu-id="20c5d-103">Make the switch to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="20c5d-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="20c5d-104">**Applies to:**</span></span>
- [<span data-ttu-id="20c5d-105">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="20c5d-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="20c5d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20c5d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="20c5d-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="20c5d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="20c5d-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="20c5d-109">마이그레이션 가이드</span><span class="sxs-lookup"><span data-stu-id="20c5d-109">Migration guides</span></span>

<span data-ttu-id="20c5d-110">끝점용 Defender로 이동을 고려하고 있는 경우 도움이 되는 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-110">If you're considering moving to Defender for Endpoint, we have guidance to help.</span></span> <span data-ttu-id="20c5d-111">다음 표에서 시나리오를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-111">In the following table, review the scenarios.</span></span> <span data-ttu-id="20c5d-112">상황에 가장 적합한 시나리오를 선택하고 권장 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20c5d-112">Select the scenario that best represents your situation, and see the recommended guidance.</span></span>

| <span data-ttu-id="20c5d-113">시나리오</span><span class="sxs-lookup"><span data-stu-id="20c5d-113">Scenario</span></span> | <span data-ttu-id="20c5d-114">지침</span><span class="sxs-lookup"><span data-stu-id="20c5d-114">Guidance</span></span> |
|:----|:----|
| <span data-ttu-id="20c5d-115">아직 끝점 보호 솔루션이 준비되지 않았고 Endpoint용 Defender에 대해 더 알고 싶을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-115">You don't have an endpoint protection solution in place yet, and you want to know more about Defender for Endpoint.</span></span> <p> <span data-ttu-id="20c5d-116">환경에서 롤아웃하기 전에 Endpoint용 Defender의 작동 방법을 확인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="20c5d-116">You want to see how Defender for Endpoint works before rolling it out in your environment.</span></span>  | [<span data-ttu-id="20c5d-117">끝점용 Microsoft Defender 평가 랩</span><span class="sxs-lookup"><span data-stu-id="20c5d-117">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
| <span data-ttu-id="20c5d-118">끝점에 대한 Defender가 이미 있으며 모든 것을 설정하고 구성하는 데 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-118">You already have Defender for Endpoint, and you want some help getting everything set up and configured.</span></span>  | [<span data-ttu-id="20c5d-119">끝점용 Microsoft Defender 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="20c5d-119">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
| <span data-ttu-id="20c5d-120">Microsoft가 아닌 엔드포인트 보호 솔루션에서 Endpoint용 Defender로 전환하고 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="20c5d-120">You're planning to switch from a non-Microsoft endpoint protection solution to Defender for Endpoint and Microsoft Defender Antivirus.</span></span> <p> <span data-ttu-id="20c5d-121">마이그레이션 프로세스와 전환 방법을 간략하게 살펴 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-121">You want to get an overview of the migration process and how to make the switch.</span></span> |[<span data-ttu-id="20c5d-122">끝점용 Microsoft Defender로 전환</span><span class="sxs-lookup"><span data-stu-id="20c5d-122">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
| <span data-ttu-id="20c5d-123">끝점용 Defender로 이미 마이그레이션하거나 온보딩한 경우</span><span class="sxs-lookup"><span data-stu-id="20c5d-123">You've already migrated or onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="20c5d-124">보안 설정 관리, 추가 기능 구성 또는 보안 정책 미세 조정과 같은 다음 단계에 대한 몇 가지 도움말을 원합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-124">You want some help with next steps, such as managing your security settings, configuring more features, or fine-tuning your security policies.</span></span> | [<span data-ttu-id="20c5d-125">끝점용 Microsoft Defender 관리, 마이그레이션 후</span><span class="sxs-lookup"><span data-stu-id="20c5d-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="do-you-have-feedback-for-us"></a><span data-ttu-id="20c5d-126">피드백이 있나요?</span><span class="sxs-lookup"><span data-stu-id="20c5d-126">Do you have feedback for us?</span></span>

<span data-ttu-id="20c5d-127">의견을 전달해주세요!</span><span class="sxs-lookup"><span data-stu-id="20c5d-127">Let us know what you think!</span></span> <span data-ttu-id="20c5d-128">페이지 아래쪽에 피드백을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="20c5d-129">계속해서 개선되고 마이그레이션 지침에 추가될 때 피드백을 고려할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20c5d-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="20c5d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20c5d-130">See also</span></span>

- [<span data-ttu-id="20c5d-131">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="20c5d-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="20c5d-132">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="20c5d-132">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="20c5d-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20c5d-133">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
