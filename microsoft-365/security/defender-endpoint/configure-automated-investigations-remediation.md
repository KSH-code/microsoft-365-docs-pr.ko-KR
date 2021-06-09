---
title: 자동화된 조사 및 수정 기능 구성
description: 끝점용 Microsoft Defender에서 자동화된 조사 및 수정 기능을 설정합니다.
keywords: 구성, 설정, 자동화, 조사, 검색, 경고, 수정, 응답
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841350"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ef216-104">끝점용 Microsoft Defender에서 자동화된 조사 및 수정 기능 구성</span><span class="sxs-lookup"><span data-stu-id="ef216-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ef216-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ef216-105">**Applies to:**</span></span>
- [<span data-ttu-id="ef216-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ef216-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ef216-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef216-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ef216-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ef216-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ef216-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="ef216-110">조직에서 [끝점용 Microsoft Defender(Endpoint용 Defender)를](/windows/security/threat-protection/) 사용하는 경우 [자동화된](/microsoft-365/security/defender-endpoint/automated-investigations) 조사 및 수정 기능을 통해 보안 운영 팀의 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-110">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="ef216-111">이 블로그 [](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)게시물에 설명된 것 처럼 이러한 기능은 보안 분석가가 위협을 조사하고 수정하는 데 걸리는 이상적인 단계와 모방합니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="ef216-112">[자동화된 조사 및 수정에 대해 자세히 알아보시겠어요.](/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="ef216-112">[Learn more about automated investigation and remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="ef216-113">자동화된 조사 및 수정을 구성하기 위해</span><span class="sxs-lookup"><span data-stu-id="ef216-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="ef216-114">[기능 켜기](#turn-on-automated-investigation-and-remediation); 및</span><span class="sxs-lookup"><span data-stu-id="ef216-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="ef216-115">[장치 그룹 설정](#set-up-device-groups).</span><span class="sxs-lookup"><span data-stu-id="ef216-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="ef216-116">자동화된 조사 및 수정 켜기</span><span class="sxs-lookup"><span data-stu-id="ef216-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="ef216-117">전역 관리자 또는 보안 관리자는 [https://securitycenter.windows.com](https://securitycenter.windows.com) Microsoft Defender 보안 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="ef216-118">탐색 창에서 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="ef216-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="ef216-119">일반 **섹션에서** 고급 기능을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef216-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="ef216-120">자동 조사 **및** **경고 자동 해결을 둘 다 니다.**</span><span class="sxs-lookup"><span data-stu-id="ef216-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="ef216-121">장치 그룹 설정</span><span class="sxs-lookup"><span data-stu-id="ef216-121">Set up device groups</span></span>

1. <span data-ttu-id="ef216-122">in the Microsoft Defender 보안 센터 ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) on the **설정** page, under **Permissions**, select **Device groups**.</span><span class="sxs-lookup"><span data-stu-id="ef216-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="ef216-123">**+ 장치 그룹 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef216-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="ef216-124">다음과 같이 하나 이상의 장치 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="ef216-125">디바이스 그룹의 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="ef216-126">자동화 **수준 목록에서** 수준(예: 전체 - 위협 자동 **수정)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef216-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="ef216-127">자동화 수준은 수정 작업이 자동으로 수행될지 승인 시에만 수행될지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="ef216-128">자세한 내용은 자동화된 조사 및 수정의 자동화 수준을 [참조합니다.](automation-levels.md)</span><span class="sxs-lookup"><span data-stu-id="ef216-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="ef216-129">구성원 **섹션에서** 하나 이상의 조건을 사용하여 장치를 식별하고 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="ef216-130">사용자 **액세스 탭에서** 만들 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) 액세스할 수 있는 사용자 그룹 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-130">On the **User access** tab, select the [Azure Active Directory groups](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="ef216-131">디바이스 **그룹** 설정이 완료되면 완료를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef216-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ef216-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ef216-132">Next steps</span></span>

- [<span data-ttu-id="ef216-133">관리 센터를 방문하여 보류 중 및 완료된 수정 작업 보기</span><span class="sxs-lookup"><span data-stu-id="ef216-133">Visit the Action Center to view pending and completed remediation actions</span></span>](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="ef216-134">보류 중인 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="ef216-134">Review and approve pending actions</span></span>](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="ef216-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef216-135">See also</span></span>

- [<span data-ttu-id="ef216-136">Endpoint용 Microsoft Defender에서 가양성/가음성 처리</span><span class="sxs-lookup"><span data-stu-id="ef216-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
