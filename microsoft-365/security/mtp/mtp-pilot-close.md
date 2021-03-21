---
title: 파일럿 Microsoft 365 Defender 프로젝트 결과 요약
description: 성적표를 완성하고, 보고서 결과를 분석하고, 앞으로 이동하는 방법을 결정하여 파일럿 Microsoft 365 Defender 프로젝트를 완료합니다.
keywords: Microsoft 위협 방지 파일럿, 파일럿 Microsoft 위협 방지 프로젝트, 프로덕션에서 Microsoft 위협 방지 평가 후의 작업, Microsoft Threat Protection 파일럿에서 배포로 전환, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f646fe7061fb0793fd9922068c9037be21a236cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920399"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="2f7da-104">Microsoft 365 Defender 파일럿 닫기 및 요약</span><span class="sxs-lookup"><span data-stu-id="2f7da-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2f7da-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2f7da-105">**Applies to:**</span></span>
- <span data-ttu-id="2f7da-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f7da-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="2f7da-107">[![계획](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="2f7da-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="2f7da-108">계획</span><span class="sxs-lookup"><span data-stu-id="2f7da-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="2f7da-109">[![준비](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="2f7da-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="2f7da-110">준비</span><span class="sxs-lookup"><span data-stu-id="2f7da-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="2f7da-111">[![공격 시뮬레이션](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="2f7da-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="2f7da-112">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="2f7da-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![닫기 및 요약](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="2f7da-114">닫기 및 요약</span><span class="sxs-lookup"><span data-stu-id="2f7da-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="2f7da-115">*여기 있습니다!*</span><span class="sxs-lookup"><span data-stu-id="2f7da-115">*You are here!*</span></span>|


<span data-ttu-id="2f7da-116">현재 닫기 및 요약 단계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="2f7da-117">도메인 컨트롤러에서 원격으로 코드를 실행하는 고급 메모리 전용 공격 시뮬레이션을 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="2f7da-118">끝점용 Microsoft Defender 및 ID용 Microsoft Defender가 도용된 악의적인 활동을 감지하고 경고를 생성하는 방법을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="2f7da-119">또한 Microsoft 365 보안 센터 포털에서 다른 컨텍스트 정보와 함께 여러 원본의 경고가 단일 인시던트로 전달된 방식도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="2f7da-120">이러한 통합을 경험하면 SOC 분석가가 조사하고 필요한 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="2f7da-121">또한 사용자가 첨부 파일을 열거나 저장하고 해당 쿼리를 기반으로 검색을 만든 인바운드 전자 메일을 식별하는 고급 헌팅 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="2f7da-122">모든 테스트가 완료된 후 프로세스가 끝났습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="2f7da-123">최종 출력은 다음이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-123">The final output should be:</span></span>

- <span data-ttu-id="2f7da-124">완료된 점수 기록표</span><span class="sxs-lookup"><span data-stu-id="2f7da-124">A completed scorecard</span></span>
- <span data-ttu-id="2f7da-125">파일럿 결과의 자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="2f7da-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="2f7da-126">앞으로 이동하는 방법에 대한 결정</span><span class="sxs-lookup"><span data-stu-id="2f7da-126">A decision on how to move forward</span></span>

<span data-ttu-id="2f7da-127">최종 출력의 보고서를 내부 이해 관계자(준비 단계에서 확인한) 및 Microsoft 담당자에게 제공합니다. [](./prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="2f7da-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-mtpeval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="2f7da-128">이러한 노력으로 제품 및 설명서를 개선하는 데 피드백을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="2f7da-129">이 시뮬레이션을 즐길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="2f7da-130">조직에서 더 큰 규모로 배운 내용을 구현하여 통합된 보안 솔루션을 가장 잘 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7da-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="2f7da-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2f7da-131">Next step</span></span>
<span data-ttu-id="2f7da-132">다음 대화형 가이드를 통해 Microsoft 365 Defender 기조에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2f7da-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="2f7da-133">Office 365용 Microsoft Defender를 사용하여 조직 보호</span><span class="sxs-lookup"><span data-stu-id="2f7da-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="2f7da-134">Microsoft Defender for Identity를 사용하여 의심스러운 활동과 잠재적인 공격을 감지</span><span class="sxs-lookup"><span data-stu-id="2f7da-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="2f7da-135">Microsoft Cloud App Security를 사용하여 위협 감지 및 경고 관리</span><span class="sxs-lookup"><span data-stu-id="2f7da-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="2f7da-136">끝점용 Microsoft Defender를 통해 위협 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="2f7da-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)