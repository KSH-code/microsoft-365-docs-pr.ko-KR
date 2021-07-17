---
title: Id에 대한 Microsoft Defender 평가 환경을 사용하도록 설정하고, MDI 인스턴스를 설정하고, MDI 센서를 설치 및 구성하고, MDI 센서가 로컬 관리자를 감지하도록 합니다.
description: 센서를 구성하고 Microsoft 365 Defender 로컬 관리자를 검색하여 Microsoft 365 Defender & 테스트 랩 또는 파일럿 환경에서 ID에 대한 Microsoft Defender를 설치합니다.
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458076"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="6f31c-103">Id에 대한 Microsoft Defender의 평가 환경 사용</span><span class="sxs-lookup"><span data-stu-id="6f31c-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="6f31c-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6f31c-104">**Applies to:**</span></span>
- <span data-ttu-id="6f31c-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f31c-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="6f31c-106">이 문서는 Id에 대한 Microsoft Defender의 평가 환경을 설정하는 프로세스의 [2단계](eval-defender-identity-overview.md) 중 2단계입니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="6f31c-107">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f31c-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="6f31c-108">다음 단계에 따라 ID용 Microsoft Defender 환경을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![Microsoft Defender 평가 환경에서 Id에 대해 Microsoft Defender를 사용하도록 설정하는 단계](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="6f31c-110">1단계. ID 인스턴스에 대한 Defender 설정</span><span class="sxs-lookup"><span data-stu-id="6f31c-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="6f31c-111">2단계. 센서 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="6f31c-112">3단계. 센서가 있는 컴퓨터의 이벤트 로그 및 프록시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="6f31c-113">4단계. Id에 Defender를 허용하여 다른 컴퓨터에서 로컬 관리자 식별</span><span class="sxs-lookup"><span data-stu-id="6f31c-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="6f31c-114">1단계.</span><span class="sxs-lookup"><span data-stu-id="6f31c-114">Step 1.</span></span> <span data-ttu-id="6f31c-115">ID 인스턴스에 대한 Defender 설정</span><span class="sxs-lookup"><span data-stu-id="6f31c-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="6f31c-116">ID용 Defender 포털에 로그인하여 인스턴스를 만든 다음 이 인스턴스를 Active Directory 환경에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="6f31c-117">단계</span><span class="sxs-lookup"><span data-stu-id="6f31c-117">Step</span></span>     |<span data-ttu-id="6f31c-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="6f31c-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6f31c-119">1 </span><span class="sxs-lookup"><span data-stu-id="6f31c-119">1</span></span>     | <span data-ttu-id="6f31c-120">ID용 Defender 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="6f31c-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="6f31c-121">빠른 시작: ID용 Microsoft Defender 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="6f31c-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="6f31c-122">2 </span><span class="sxs-lookup"><span data-stu-id="6f31c-122">2</span></span>     | <span data-ttu-id="6f31c-123">커넥트 대한 Defender 인스턴스를 Active Directory 포리스트에 추가</span><span class="sxs-lookup"><span data-stu-id="6f31c-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="6f31c-124">빠른 시작: 커넥트 포리스트로 설정</span><span class="sxs-lookup"><span data-stu-id="6f31c-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="6f31c-125">2단계.</span><span class="sxs-lookup"><span data-stu-id="6f31c-125">Step 2.</span></span> <span data-ttu-id="6f31c-126">센서 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-126">Install and configure the sensor</span></span>

<span data-ttu-id="6f31c-127">다음으로, 도메인 컨트롤러 및 AD FS 서버의 ID에 대한 Defender 센서를 다운로드, 설치 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="6f31c-128">단계</span><span class="sxs-lookup"><span data-stu-id="6f31c-128">Step</span></span>     |<span data-ttu-id="6f31c-129">추가 정보</span><span class="sxs-lookup"><span data-stu-id="6f31c-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6f31c-130">1 </span><span class="sxs-lookup"><span data-stu-id="6f31c-130">1</span></span>     | <span data-ttu-id="6f31c-131">필요한 ID 센서에 대한 Microsoft Defender 수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="6f31c-132">Id에 대한 Microsoft Defender 용량 계획</span><span class="sxs-lookup"><span data-stu-id="6f31c-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="6f31c-133">2 </span><span class="sxs-lookup"><span data-stu-id="6f31c-133">2</span></span>     | <span data-ttu-id="6f31c-134">센서 설치 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="6f31c-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="6f31c-135">빠른 시작: Id용 Microsoft Defender 센서 설정 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="6f31c-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="6f31c-136">3 </span><span class="sxs-lookup"><span data-stu-id="6f31c-136">3</span></span>     | <span data-ttu-id="6f31c-137">Id용 Defender 센서 설치</span><span class="sxs-lookup"><span data-stu-id="6f31c-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="6f31c-138">빠른 시작: Id용 Microsoft Defender 센서 설치</span><span class="sxs-lookup"><span data-stu-id="6f31c-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="6f31c-139">4 </span><span class="sxs-lookup"><span data-stu-id="6f31c-139">4</span></span>     | <span data-ttu-id="6f31c-140">센서 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-140">Configure the sensor</span></span>       |  [<span data-ttu-id="6f31c-141">Id에 대한 Microsoft Defender 센서 설정 구성 </span><span class="sxs-lookup"><span data-stu-id="6f31c-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="6f31c-142">3단계.</span><span class="sxs-lookup"><span data-stu-id="6f31c-142">Step 3.</span></span> <span data-ttu-id="6f31c-143">센서가 있는 컴퓨터의 이벤트 로그 및 프록시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="6f31c-144">센서를 설치한 컴퓨터의 경우 Windows 로그 수집 및 인터넷 프록시 설정을 구성하여 검색 기능을 사용하도록 설정하고 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="6f31c-145">단계</span><span class="sxs-lookup"><span data-stu-id="6f31c-145">Step</span></span>     |<span data-ttu-id="6f31c-146">추가 정보</span><span class="sxs-lookup"><span data-stu-id="6f31c-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6f31c-147">1 </span><span class="sxs-lookup"><span data-stu-id="6f31c-147">1</span></span>     | <span data-ttu-id="6f31c-148">이벤트 Windows 컬렉션 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="6f31c-149">이벤트 Windows 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="6f31c-150">2 </span><span class="sxs-lookup"><span data-stu-id="6f31c-150">2</span></span>     | <span data-ttu-id="6f31c-151">인터넷 프록시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="6f31c-152">Id 센서에 대한 Microsoft Defender에 대한 끝점 프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6f31c-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="6f31c-153">4단계.</span><span class="sxs-lookup"><span data-stu-id="6f31c-153">Step 4.</span></span> <span data-ttu-id="6f31c-154">Id에 Defender를 허용하여 다른 컴퓨터에서 로컬 관리자 식별</span><span class="sxs-lookup"><span data-stu-id="6f31c-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="6f31c-155">Id 측면 이동 경로 검색을 위한 Microsoft Defender는 특정 컴퓨터의 로컬 관리자를 식별하는 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="6f31c-156">이러한 쿼리는 ID 서비스용 Defender 계정을 사용하여 SAM-R 프로토콜을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="6f31c-157">Windows 클라이언트 및 서버에서 ID용 Defender 계정이 SAM-R을 수행할 수 있도록 허용하려면 네트워크 액세스 정책에 나열된 구성된 계정 외에도 ID용 Defender 서비스 계정을 추가하도록 그룹 정책을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f31c-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="6f31c-158">도메인 컨트롤러를 제외한 모든 컴퓨터에 그룹 **정책을 적용해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f31c-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="6f31c-159">이 작업을 하는 방법에 대한 지침은 SAM에 대한 원격 호출을 하도록 [Id에 대한 Microsoft Defender 구성을 참조하세요.](/defender-for-identity/install-step8-samr)</span><span class="sxs-lookup"><span data-stu-id="6f31c-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="6f31c-160">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6f31c-160">Next steps</span></span>

<span data-ttu-id="6f31c-161">3단계 중 3단계: [Id에 대한 Microsoft Defender 파일럿](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="6f31c-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="6f31c-162">ID에 대한 [Microsoft Defender 평가 개요로 돌아가기](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f31c-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="6f31c-163">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f31c-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>