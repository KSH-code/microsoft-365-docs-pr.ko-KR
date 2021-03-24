---
title: 표시기 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 파일 해시, IP 주소, URL 또는 도메인에 대한 표시기를 만들 수 있습니다.
keywords: 관리, 허용, 차단, 차단, 클린, 악성, 파일 해시, ip 주소, URL, 도메인
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fc3bce7130dbdcec76a67df70eb1a6c72474013e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072087"
---
# <a name="create-indicators"></a><span data-ttu-id="9b302-104">표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="9b302-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9b302-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9b302-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b302-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9b302-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9b302-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b302-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="9b302-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9b302-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b302-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="9b302-110">IoC(손상 표시기) 일치는 모든 끝점 보호 솔루션에서 필수적인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="9b302-111">SecOps는 이 기능을 통해 검색 및 차단(예방 및 응답)에 대한 표시기 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="9b302-112">엔터티의 검색, 방지 및 제외를 정의하는 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="9b302-113">수행되는 작업과 작업을 적용할 기간 및 적용할 장치 그룹의 범위를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="9b302-114">현재 지원되는 원본은 Endpoint용 Defender의 클라우드 검색 엔진, 자동화된 조사 및 수정 엔진 및 끝점 방지 엔진(Microsoft Defender AV)입니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender AV).</span></span>

<span data-ttu-id="9b302-115">**클라우드 검색 엔진**</span><span class="sxs-lookup"><span data-stu-id="9b302-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="9b302-116">Endpoint용 Defender의 클라우드 검색 엔진은 정기적으로 수집된 데이터를 검색하고 설정한 지표와 일치를 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="9b302-117">일치하는 경우 IoC에 대해 지정한 설정에 따라 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="9b302-118">**끝점 방지 엔진**</span><span class="sxs-lookup"><span data-stu-id="9b302-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="9b302-119">동일한 표시기 목록은 방지 에이전트에 의해 존중됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="9b302-120">즉, Microsoft Defender AV가 구성된 기본 AV인 경우 일치하는 표시기가 설정에 따라 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="9b302-121">예를 들어 작업이 "경고 및 차단"이면 Microsoft Defender AV는 파일 실행(차단 및 재구성)을 방지하고 해당 경고가 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="9b302-122">반면 동작이 "허용"으로 설정된 경우 Microsoft Defender AV는 파일을 검색하거나 실행하지 못하도록 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="9b302-123">**자동화된 조사 및 수정 엔진**</span><span class="sxs-lookup"><span data-stu-id="9b302-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="9b302-124">자동화된 조사 및 수정은 동일하게 행동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="9b302-125">표시기가 "허용"으로 설정된 경우 자동화된 조사 및 수정은 해당 지표에 대한 "나쁜" 판정을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="9b302-126">"차단"으로 설정된 경우 자동화된 조사 및 수정은 이를 "불량"으로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="9b302-127">현재 지원되는 작업은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-127">The current supported actions are:</span></span>
- <span data-ttu-id="9b302-128">허용</span><span class="sxs-lookup"><span data-stu-id="9b302-128">Allow</span></span>
- <span data-ttu-id="9b302-129">경고만</span><span class="sxs-lookup"><span data-stu-id="9b302-129">Alert only</span></span>
- <span data-ttu-id="9b302-130">경고 및 차단</span><span class="sxs-lookup"><span data-stu-id="9b302-130">Alert and block</span></span>


<span data-ttu-id="9b302-131">다음에 대한 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="9b302-132">파일</span><span class="sxs-lookup"><span data-stu-id="9b302-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="9b302-133">IP 주소, URL/도메인</span><span class="sxs-lookup"><span data-stu-id="9b302-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="9b302-134">인증서</span><span class="sxs-lookup"><span data-stu-id="9b302-134">Certificates</span></span>](indicator-certificates.md)


>[!NOTE]
><span data-ttu-id="9b302-135">테넌트당 표시기는 15,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b302-135">There is a limit of 15,000 indicators per tenant.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9b302-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9b302-136">Related topics</span></span>

- [<span data-ttu-id="9b302-137">상황적 IoC 만들기</span><span class="sxs-lookup"><span data-stu-id="9b302-137">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="9b302-138">끝점 표시기 API에 Microsoft Defender 사용</span><span class="sxs-lookup"><span data-stu-id="9b302-138">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="9b302-139">파트너 통합 솔루션 사용</span><span class="sxs-lookup"><span data-stu-id="9b302-139">Use partner integrated solutions</span></span>](partner-applications.md)
