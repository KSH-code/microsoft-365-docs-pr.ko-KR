---
title: Id용 Microsoft Defender에 대한 아키텍처 요구 사항 및 기술 프레임워크, 아키텍처 다이어그램, MDI 검토
description: Microsoft Defender for Identity에 대한 기술 다이어그램은 Microsoft 365 Defender 랩 또는 파일럿 환경을 구축하기 전에 Microsoft 365 ID를 이해하는 데 도움이 됩니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8f0c736d07a2a66420416d30ae2dc45ae5fee37a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458710"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a><span data-ttu-id="54f94-103">Microsoft Defender for Identity에 대한 아키텍처 요구 사항 및 주요 개념 검토</span><span class="sxs-lookup"><span data-stu-id="54f94-103">Review architecture requirements and key concepts for Microsoft Defender for Identity</span></span>


<span data-ttu-id="54f94-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="54f94-104">**Applies to:**</span></span>
- <span data-ttu-id="54f94-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54f94-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="54f94-106">이 문서는 Id에 대한 Microsoft Defender의 평가 환경을 설정하는 프로세스의 [1단계](eval-defender-identity-overview.md) 중 3단계입니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-106">This article is [Step 1 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="54f94-107">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="54f94-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="54f94-108">Id에 대해 Microsoft Defender를 사용하도록 설정하기 전에 아키텍처를 이해하고 요구 사항을 충족할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-108">Before enabling Microsoft Defender for Identity, be sure you understand the architecture and can meet the requirements.</span></span>

<span data-ttu-id="54f94-109">Id용 Microsoft Defender는 기계 학습 및 동작 분석을 사용하여 클라우드 ID와 관련된 사용자 로그인 위험을 감지하고 사전 예방하는 것과 함께 사내 네트워크에서 공격을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-109">Microsoft Defender for Identity uses machine learning and behavioral analytics to identify attacks across your on-premises network along with detecting and proactively preventing user sign-in risks associated with cloud identities.</span></span> <span data-ttu-id="54f94-110">자세한 내용은 Id에 [대한 Microsoft Defender란?을 참조하세요.](/defender-for-identity/what-is)</span><span class="sxs-lookup"><span data-stu-id="54f94-110">For more information, see [What is Microsoft Defender for Identity?](/defender-for-identity/what-is)</span></span>

<span data-ttu-id="54f94-111">Id에 대한 Defender는 Azure AD(Active Directory)에 동기화된 사용자 및/또는 Azure Active Directory 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-111">Defender for Identity protects your on-premises Active Directory users and/or users synced to your Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="54f94-112">Azure AD 사용자로만 만들어진 환경을 보호하기 위해 [Azure AD ID 보호를 참조하세요.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="54f94-112">To protect an environment made up of only Azure AD users, see [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="54f94-113">아키텍처 이해</span><span class="sxs-lookup"><span data-stu-id="54f94-113">Understand the architecture</span></span>

<span data-ttu-id="54f94-114">다음 다이어그램은 Id용 Defender에 대한 기준 아키텍처를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-114">The following diagram illustrates the baseline architecture for Defender for Identity.</span></span> 

![Id용 Microsoft Defender 아키텍처](../../media/defender/m365-defender-identity-architecture.png)

<span data-ttu-id="54f94-116">이 그림에서는 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-116">In this illustration:</span></span>
- <span data-ttu-id="54f94-117">AD 도메인 컨트롤러에 설치된 센서는 로그 및 네트워크 트래픽을 구문 분석하고 분석 및 보고를 위해 ID를 위해 Microsoft Defender로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-117">Sensors installed on AD domain controllers parse logs and network traffic and send them to Microsoft Defender for Identity for analysis and reporting.</span></span>
-  <span data-ttu-id="54f94-118">Azure AD가 페더레이션 인증(그림의 점선)을 사용하도록 구성된 경우 센서는 AD FS(Active Directory Federation Services)를 구문 분석할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-118">Sensors can also parse Active Directory Federation Services (AD FS) when Azure AD is configured to use federated authentication (dotted line in illustration).</span></span> 
- <span data-ttu-id="54f94-119">Microsoft Defender for Identity는 XDR(확장 Microsoft 365 Defender 및 응답)에 대한 신호를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-119">Microsoft Defender for Identity shares signals to Microsoft 365 Defender for extended detection and response (XDR).</span></span>


<span data-ttu-id="54f94-120">ID용 Defender 센서는 다음 서버에 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-120">Defender for Identity sensors can be directly installed on the following servers:</span></span>

- <span data-ttu-id="54f94-121">도메인 컨트롤러: 센서는 전용 서버 또는 포트 미러링 구성 없이 도메인 컨트롤러 트래픽을 직접 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-121">Domain controllers: The sensor directly monitors domain controller traffic, without the need for a dedicated server, or configuration of port mirroring.</span></span>
- <span data-ttu-id="54f94-122">AD FS: 센서는 네트워크 트래픽 및 인증 이벤트를 직접 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-122">AD FS: The sensor directly monitors network traffic and authentication events.</span></span>

<span data-ttu-id="54f94-123">Id에 대한 Defender의 아키텍처에 대한 자세한 내용은 id와의 통합을 포함하여 Cloud App Security [Microsoft Defender for Identity architecture를 참조합니다.](/defender-for-identity/architecture)</span><span class="sxs-lookup"><span data-stu-id="54f94-123">For a deeper look into the architecture of Defender for Identity, including integration with Cloud App Security, see [Microsoft Defender for Identity architecture](/defender-for-identity/architecture).</span></span>


## <a name="understand-key-concepts"></a><span data-ttu-id="54f94-124">주요 개념 이해</span><span class="sxs-lookup"><span data-stu-id="54f94-124">Understand key concepts</span></span>

<span data-ttu-id="54f94-125">다음 표에서는 ID에 대한 Microsoft Defender를 평가, 구성 및 배포할 때 이해해야 하는 주요 개념을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Identity.</span></span>


|<span data-ttu-id="54f94-126">개념</span><span class="sxs-lookup"><span data-stu-id="54f94-126">Concept</span></span>  |<span data-ttu-id="54f94-127">설명</span><span class="sxs-lookup"><span data-stu-id="54f94-127">Description</span></span> |<span data-ttu-id="54f94-128">추가 정보</span><span class="sxs-lookup"><span data-stu-id="54f94-128">More information</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="54f94-129">모니터링된 활동</span><span class="sxs-lookup"><span data-stu-id="54f94-129">Monitored activities</span></span> | <span data-ttu-id="54f94-130">ID에 대한 Defender는 조직 내에서 생성된 신호를 모니터링하여 의심스러우거나 악의적인 활동을 감지하고 각 잠재적 위협의 유효성을 확인하여 효과적으로 판단하고 대응할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-130">Defender for Identity monitors signals generated from within your organization to detect suspicious or malicious activity and helps you determine the validity of each potential threat so that you can effectively triage and respond.</span></span>  |  [<span data-ttu-id="54f94-131">Id 모니터링 활동용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="54f94-131">Microsoft Defender for Identity monitored activities</span></span>](/defender-for-identity/monitored-activities)       |
| <span data-ttu-id="54f94-132">보안 경고</span><span class="sxs-lookup"><span data-stu-id="54f94-132">Security alerts</span></span>    | <span data-ttu-id="54f94-133">ID 보안 경고에 대한 Defender는 네트워크의 센서에서 감지된 의심스러운 활동과 각 위협에 관련된 공격자 및 컴퓨터에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-133">Defender for Identity security alerts explain the suspicious activities detected by sensors on your network along with the actors and computers involved in each threat.</span></span>   | [<span data-ttu-id="54f94-134">Id 보안 경고에 대한 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="54f94-134">Microsoft Defender for Identity Security Alerts</span></span>](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| <span data-ttu-id="54f94-135">엔터티 프로필</span><span class="sxs-lookup"><span data-stu-id="54f94-135">Entity profiles</span></span>    | <span data-ttu-id="54f94-136">엔터티 프로필은 액세스 기록과 함께 사용자, 컴퓨터, 장치 및 리소스에 대한 포괄적인 심층 조사를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-136">Entity profiles provide a comprehensive deep-dive investigation of users, computers, devices, and resources along with their access history.</span></span>   | [<span data-ttu-id="54f94-137">엔터티 프로필 이해</span><span class="sxs-lookup"><span data-stu-id="54f94-137">Understanding entity profiles</span></span>](/defender-for-identity/entity-profiles)  |
| <span data-ttu-id="54f94-138">측면 이동 경로</span><span class="sxs-lookup"><span data-stu-id="54f94-138">Lateral movement paths</span></span>    | <span data-ttu-id="54f94-139">MDI 보안 인사이트의 주요 구성 요소는 공격자가 중요하지 않은 계정을 사용하여 네트워크 전체의 중요한 계정 또는 컴퓨터 액세스 권한을 얻는 측면 이동 경로를 식별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-139">A key component of MDI security insights is identifying lateral movement paths in which an attacker uses non-sensitive accounts to gain access to sensitive accounts or machines throughout your network.</span></span>  | [<span data-ttu-id="54f94-140">Microsoft Defender for Identity 측면 이동 경로(LMP)</span><span class="sxs-lookup"><span data-stu-id="54f94-140">Microsoft Defender for Identity Lateral Movement Paths (LMPs)</span></span>](/defender-for-identity/use-case-lateral-movement-path)  |
| <span data-ttu-id="54f94-141">네트워크 이름 확인</span><span class="sxs-lookup"><span data-stu-id="54f94-141">Network Name Resolution</span></span>    |  <span data-ttu-id="54f94-142">NNR(네트워크 이름 확인)은 네트워크 트래픽, Windows 이벤트, ETW 등을 기반으로 활동을 캡처하고 이 원시 데이터를 각 활동에 관련된 관련 컴퓨터와 상관 관계가 있는 MDI 기능의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-142">Network Name Resolution (NNR) is a component of MDI functionality which captures activities based on network traffic, Windows events, ETW, etc. and correlates this raw data to the relevant computers involved in each activity.</span></span>       | [<span data-ttu-id="54f94-143">네트워크 이름 확인이란?</span><span class="sxs-lookup"><span data-stu-id="54f94-143">What is Network Name Resolution?</span></span>](/defender-for-identity/nnr-policy)      |
| <span data-ttu-id="54f94-144">보고서</span><span class="sxs-lookup"><span data-stu-id="54f94-144">Reports</span></span>    | <span data-ttu-id="54f94-145">Id용 Defender 보고서를 사용하면 시스템 및 엔터티 상태 정보를 제공하는 보고서를 예약하거나 즉시 생성하고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-145">Defender for Identity reports allow you to schedule or immediately generate and download reports that provide system and entity status information.</span></span>  <span data-ttu-id="54f94-146">사용자 환경에서 감지된 시스템 상태, 보안 경고 및 잠재적인 측면 이동 경로에 대한 보고서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-146">You can create reports about system health, security alerts, and potential lateral movement paths detected in your environment.</span></span>   | [<span data-ttu-id="54f94-147">Microsoft Defender for Identity Reports </span><span class="sxs-lookup"><span data-stu-id="54f94-147">Microsoft Defender for Identity Reports </span></span>](/defender-for-identity/reports)       |
| <span data-ttu-id="54f94-148">역할 그룹</span><span class="sxs-lookup"><span data-stu-id="54f94-148">Role groups</span></span>    | <span data-ttu-id="54f94-149">Id에 대한 Defender는 관리자, 사용자 및 뷰어를 포함하는 조직의 특정 보안 및 규정 준수 요구에 따라 데이터를 보호하기 위해 역할 기반 그룹 및 위임된 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-149">Defender for Identity offers role-based groups and delegated access to safeguard data according to your organization's specific security and compliance needs which includes Administrators, Users and Viewers.</span></span>        |  [<span data-ttu-id="54f94-150">ID용 Microsoft Defender 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="54f94-150">Microsoft Defender for Identity role groups</span></span>](/defender-for-identity/role-groups)       |
| <span data-ttu-id="54f94-151">관리 포털</span><span class="sxs-lookup"><span data-stu-id="54f94-151">Administrative portal</span></span>    |  <span data-ttu-id="54f94-152">보안 센터 Microsoft 365 외에도 ID 포털용 Defender cab을 사용하여 의심스러운 활동을 모니터링하고 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-152">In addition to the Microsoft 365 Security Center, the Defender for Identity portal cab be used to monitor and respond to suspicious activity.</span></span>      | [<span data-ttu-id="54f94-153">Microsoft Defender for Identity 포털 작업</span><span class="sxs-lookup"><span data-stu-id="54f94-153">Working with the Microsoft Defender for Identity portal</span></span>](/defender-for-identity/workspace-portal)        |
| <span data-ttu-id="54f94-154">Microsoft Cloud App Security 통합</span><span class="sxs-lookup"><span data-stu-id="54f94-154">Microsoft Cloud App Security integration</span></span>   | <span data-ttu-id="54f94-155">Microsoft Cloud App Security Microsoft Defender for Identity와 통합하여 클라우드 앱과 사내 모두 하이브리드 환경에서 UEBA(사용자 엔터티 동작 분석)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-155">Microsoft Cloud App Security integrates with Microsoft Defender for Identity to provide user entity behavioral analytics (UEBA) across a hybrid environment - both cloud app and on-premises</span></span>   | <span data-ttu-id="54f94-156">Microsoft Defender for Identity 통합</span><span class="sxs-lookup"><span data-stu-id="54f94-156">Microsoft Defender for Identity integration</span></span>  |
| | | |


## <a name="review-prerequisites"></a><span data-ttu-id="54f94-157">선행 준비 검토</span><span class="sxs-lookup"><span data-stu-id="54f94-157">Review prerequisites</span></span>

<span data-ttu-id="54f94-158">Id에 대한 Defender는 몇 가지 선행 조건 작업을 필요로 하여 프레미스 ID 및 네트워킹 구성 요소가 최소 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="54f94-158">Defender for Identity requires some prerequisite work to ensure that your on-premises identity and networking components meet minimum requirements.</span></span> <span data-ttu-id="54f94-159">이 문서를 검사 목록으로 사용하여 환경이 준비되도록 합니다. [Microsoft Defender for Identity prerequisites](/defender-for-identity/prerequisites).</span><span class="sxs-lookup"><span data-stu-id="54f94-159">Use this article as a checklist to ensure your environment is ready: [Microsoft Defender for Identity prerequisites](/defender-for-identity/prerequisites).</span></span>


## <a name="next-steps"></a><span data-ttu-id="54f94-160">다음 단계</span><span class="sxs-lookup"><span data-stu-id="54f94-160">Next steps</span></span>

<span data-ttu-id="54f94-161">3단계 중 2단계: ID에 대한 평가 [환경 Defender 사용](eval-defender-identity-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="54f94-161">Step 2 of 3: [Enable the evaluation environment Defender for Identity](eval-defender-identity-enable-eval.md)</span></span>

<span data-ttu-id="54f94-162">ID에 대한 [Microsoft Defender 평가 개요로 돌아가기](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="54f94-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="54f94-163">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="54f94-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span> 