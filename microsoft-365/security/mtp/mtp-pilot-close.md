---
title: 파일럿 Microsoft Threat Protection 프로젝트 결과 요약
description: 성과 기록표를 완성 하 고, 보고서의 결과를 분석 하 고, 앞으로 이동 하는 방법을 결정 하 여 파일럿 Microsoft 위협 보호 프로젝트를 마무리 합니다.
keywords: Microsoft Threat protection 파일럿, Microsoft threat Protection 프로젝트를 파일럿으로 실행 한 후에 수행할 작업, 프로덕션에서 Microsoft 위협 보호를 평가한 후 수행 해야 하는 작업, Microsoft Threat Protection 파일럿에서 배포로 전환, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화 된 조사, 개선, 고급 구하기
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1a7b87432ce1eb16c29f462fb4865bfa5c5e2201
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418100"
---
# <a name="closing-and-summarizing-your-microsoft-threat-protection-pilot"></a><span data-ttu-id="7c3f6-104">Microsoft Threat Protection 파일럿 테스트 종료 및 요약</span><span class="sxs-lookup"><span data-stu-id="7c3f6-104">Closing and summarizing your Microsoft Threat Protection pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7c3f6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7c3f6-105">**Applies to:**</span></span>
- <span data-ttu-id="7c3f6-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="7c3f6-106">Microsoft Threat Protection</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="파일럿 Microsoft Threat Protection 프로젝트 계획" />
      <br/><span data-ttu-id="7c3f6-108">만들려는 </a></span><span class="sxs-lookup"><span data-stu-id="7c3f6-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비" />
      <br/><span data-ttu-id="7c3f6-110">함 </a></span><span class="sxs-lookup"><span data-stu-id="7c3f6-110">Prepare </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Microsoft Threat Protection 공격 시뮬레이션 실행" />
      <br/><span data-ttu-id="7c3f6-112">공격 시뮬레이트 </a></span><span class="sxs-lookup"><span data-stu-id="7c3f6-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Microsoft Threat Protection 파일럿을 닫고 요약 합니다." />
      <br/><span data-ttu-id="7c3f6-114">닫기 및 요약 </a></span><span class="sxs-lookup"><span data-stu-id="7c3f6-114">Close and summarize </a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="7c3f6-115">현재 종료 및 요약 단계가 진행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-115">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="7c3f6-116">이제 도메인 컨트롤러에서 코드를 원격으로 실행 한 고급 메모리 전용 공격 시뮬레이션이 실행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-116">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="7c3f6-117">Microsoft Defender ATP 및 Azure ATP에서 stealthy 악성 활동에 대 한 경고를 검색 하 고 만드는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-117">You’ve seen how Microsoft Defender ATP and Azure ATP detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="7c3f6-118">또한 다른 상황 정보를 Microsoft 365 보안 센터 포털의 단일 인시던트에 함께 사용 하 여 다양 한 원본의 알림이 제공 되는 방식에 대해 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-118">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="7c3f6-119">이러한 통합이 발생 하면 SOC 분석가가 필요한 작업을 조사 하 고 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-119">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="7c3f6-120">또한 사용자가 첨부 파일을 열거나 저장 한 후 해당 쿼리를 기반으로 검색을 만든 인바운드 전자 메일을 식별 하는 고급 구하기 쿼리를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-120">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="7c3f6-121">모든 테스트가 완료 된 후 프로세스의 끝에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-121">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="7c3f6-122">최종 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-122">The final output should be:</span></span>

- <span data-ttu-id="7c3f6-123">완성 된 성과 기록표</span><span class="sxs-lookup"><span data-stu-id="7c3f6-123">A completed scorecard</span></span>
- <span data-ttu-id="7c3f6-124">파일럿의 결과에 대 한 자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="7c3f6-124">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="7c3f6-125">앞으로 이동 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-125">A decision on how to move forward</span></span>

<span data-ttu-id="7c3f6-126">최종 결과의 보고서에 내부 관련자 ( [준비](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) 단계에서 확인) 및 Microsoft 연락처를 모두 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-126">Present the reports from your final output both internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="7c3f6-127">이러한 노력을 통해 제품 및 문서를 개선 하는 데 모든 의견을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-127">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="7c3f6-128">이 시뮬레이션을 사용할 예정 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-128">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="7c3f6-129">통합 보안 솔루션을 최대한 활용 하기 위해 조직의 대규모 확장에 대해 배운 내용을 구현 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-129">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="7c3f6-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7c3f6-130">Next step</span></span>
<span data-ttu-id="7c3f6-131">다음 대화형 가이드를 통해 Microsoft Threat Protection 핵심 요소로에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-131">Learn more about the Microsoft Threat Protection pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="7c3f6-132">Microsoft Defender for Office 365를 사용 하 여 조직 보호</span><span class="sxs-lookup"><span data-stu-id="7c3f6-132">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="7c3f6-133">Id 용 Microsoft Defender를 사용 하 여 의심 스러운 활동 및 잠재적 공격 감지</span><span class="sxs-lookup"><span data-stu-id="7c3f6-133">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="7c3f6-134">Microsoft Cloud App Security를 사용 하 여 위협 검색 및 알림 관리</span><span class="sxs-lookup"><span data-stu-id="7c3f6-134">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="7c3f6-135">끝점에 대 한 Microsoft Defender를 사용 하 여 위협 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="7c3f6-135">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
