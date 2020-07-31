---
title: 조직의 데이터 개인 정보 취급 방침 모니터링 및 대응
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: 감사 및 경고 정책 및 데이터 주체 요청을 사용 하 여 개인 데이터 인시던트를 모니터링 하 고 대응 합니다.
ms.openlocfilehash: 8fdba5799ca9ee97a013c1322e5e79f6bf38764a
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522076"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="3a8c2-103">조직의 데이터 개인 정보 취급 방침 모니터링 및 대응</span><span class="sxs-lookup"><span data-stu-id="3a8c2-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="3a8c2-104">Microsoft 365 기능을 사용 하 여 관련 기능을 operationalize 때 조직의 데이터 개인 정보 인시던트를 모니터링, 조사 및 대응 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="3a8c2-105">이러한 각 단계에 대 한 프로세스, 절차 및 기타 설명서도 규정 된 본문에 대 한 준수를 시연 하는 것이 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="3a8c2-106">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-106">These include:</span></span> 

- <span data-ttu-id="3a8c2-107">감사 및 경고 정책</span><span class="sxs-lookup"><span data-stu-id="3a8c2-107">Auditing and alert policies</span></span>
- <span data-ttu-id="3a8c2-108">데이터 주체 요청 (콘텐츠 검색 및 eDiscovery 포함)</span><span class="sxs-lookup"><span data-stu-id="3a8c2-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="3a8c2-109">추가 조사 도구 및 보고</span><span class="sxs-lookup"><span data-stu-id="3a8c2-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="3a8c2-110">모니터링 및 응답 도구 사용에 영향을 주는 데이터 개인 정보 규정</span><span class="sxs-lookup"><span data-stu-id="3a8c2-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="3a8c2-111">다음은 정보 거 버 넌 스 컨트롤과 관련이 있을 수 있는 데이터 개인 정보 규정의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="3a8c2-112">LGPD 문서 46</span><span class="sxs-lookup"><span data-stu-id="3a8c2-112">LGPD Article 46</span></span>
- <span data-ttu-id="3a8c2-113">LGPD 문서 48</span><span class="sxs-lookup"><span data-stu-id="3a8c2-113">LGPD Article 48</span></span>
- <span data-ttu-id="3a8c2-114">GDPR 문서 (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="3a8c2-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="3a8c2-115">GDPR 문서 (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="3a8c2-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="3a8c2-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="3a8c2-117">164.308 (a) (1) (2) (D)</span><span class="sxs-lookup"><span data-stu-id="3a8c2-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="3a8c2-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="3a8c2-119">164.308 (a) (6) (ii)</span><span class="sxs-lookup"><span data-stu-id="3a8c2-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="3a8c2-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="3a8c2-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="3a8c2-121">164.312(b))</span></span>
- <span data-ttu-id="3a8c2-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="3a8c2-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="3a8c2-123">자세한 내용은 [데이터 개인 정보 보호 위험 평가 및 중요 한 정보 식별](information-protection-deploy-assess.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="3a8c2-124">데이터 개인 정보 규정은 일반적으로 모니터링 및 대응을 위해 다음을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="3a8c2-125">개인 데이터의 저장, 공유 및 처리와 관련 된 활동에 대 한 감사, 경고 및 보고</span><span class="sxs-lookup"><span data-stu-id="3a8c2-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="3a8c2-126">DSR (데이터 주체 요청)에 응답 하 고, 경우에 따라 조사 및 기타 관리 조치를 수행 하 여 이러한 요청을 준수 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="3a8c2-127">조직에서는 기타 규정 요구 사항 또는 비즈니스 이유와 같은 다른 목적으로 모니터링 및 대응 활동을 수행 하고자 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="3a8c2-128">데이터 개인 정보에 대 한 모니터링 및 대응 구성표 설정은 전체 모니터링 및 대응 계획, 구현 및 관리의 일부로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="3a8c2-129">이 문서에서는 365 Microsoft 365에서 데이터 개인 정보 규정에 대 한 모니터링 및 대응 체계를 시작 하는 데 도움이 되는 다음과 같은 사항을 설명 하는 유용한 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="3a8c2-130">다양 한 데이터 형식 및 원본에 대해 사용할 수 있는 일상적인 모니터링, 조사 및 보고 기술</span><span class="sxs-lookup"><span data-stu-id="3a8c2-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="3a8c2-131">Dsr (데이터 주체 요청) 및 익명화, 교정, 삭제와 같은 교정 작업을 처리 하는 데 필요한 메커니즘</span><span class="sxs-lookup"><span data-stu-id="3a8c2-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="3a8c2-132">보안 및 준수 센터의 감사 및 경고 정책</span><span class="sxs-lookup"><span data-stu-id="3a8c2-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="3a8c2-133">감사, 고급 감사 및 경고 정책을 설정 하려면 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="3a8c2-134">통합 감사</span><span class="sxs-lookup"><span data-stu-id="3a8c2-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="3a8c2-135">사서함 감사</span><span class="sxs-lookup"><span data-stu-id="3a8c2-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="3a8c2-136">고급 감사</span><span class="sxs-lookup"><span data-stu-id="3a8c2-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="3a8c2-137">알림 정책</span><span class="sxs-lookup"><span data-stu-id="3a8c2-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="3a8c2-138">GDPR 및 CCPA에 대 한 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="3a8c2-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="3a8c2-139">Microsoft 365에서 DSR에 응답 하는 방법에 대 한 자세한 내용은 [GDPR 및 CCPA에 대 한 데이터 주체 요청](../compliance/gdpr-dsr-office365.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="3a8c2-140">Microsoft Stream에서 삭제 된 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="3a8c2-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="3a8c2-141">Microsoft Stream의 경우 사용자가 Azure Active Directory에서 삭제 되는 경우 (Azure AD)이 지점 이전에 게시 된 스트림 비디오와 연결 된 경우 해당 전자 메일 주소는 비디오와 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="3a8c2-142">제거 하려면 [Microsoft Stream에서 삭제 된 사용자 관리](https://docs.microsoft.com/stream/managing-deleted-users) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="3a8c2-143">추가 조사 도구</span><span class="sxs-lookup"><span data-stu-id="3a8c2-143">Additional investigative tools</span></span>

<span data-ttu-id="3a8c2-144">다음은 조직에서 데이터 개인 정보 보호 관련 인시던트를 모니터링, 조사 및 수정 하는 데 유용할 수 있는 두 가지 추가 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="3a8c2-145">사용자 [의 참가자 위험 관리 microsoft 365에서](../compliance/insider-risk-management.md)조직의 위험한 활동을 감지, 조사 하 고 작업을 수행할 수 있도록 하 여 내부 위험을 최소화 하는 데 도움이 되는 microsoft 준수 관리 센터의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="3a8c2-146">Microsoft [365의 데이터 조사](../compliance/overview-data-investigations.md)에서 microsoft 365의 중요, 악성 또는 잘못 된 데이터를 검색 하 고 문제를 수정 하는 데 적절 한 조치를 취하는 상황을 조사 하는 microsoft 준수 관리 센터의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8c2-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
