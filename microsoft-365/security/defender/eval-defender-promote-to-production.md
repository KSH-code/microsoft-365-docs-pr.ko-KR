---
title: 프로덕션 Microsoft 365 Defender 환경 홍보, Microsoft 365 Defender 평가, 평가 시도, 평가 유지, 프로덕션 평가
description: 이 문서를 사용하여 MDI, MDO, MDE 및 MCAS를 MDI 또는 M365D의 라이브 환경으로 Microsoft 365 Defender 홍보할 수 있습니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458750"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="1feaf-103">프로덕션 Microsoft 365 Defender 환경으로 승격</span><span class="sxs-lookup"><span data-stu-id="1feaf-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="1feaf-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1feaf-104">**Applies to:**</span></span>
- <span data-ttu-id="1feaf-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1feaf-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="1feaf-106">평가 환경을 Microsoft 365 Defender 환경을 프로덕션 환경으로 승격하기 위해 먼저 필요한 라이선스를 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="1feaf-107">eval 환경 [](eval-create-eval-environment.md) 만들기의 단계를 수행하고 평가판 시작을 Office 365 E5 라이선스를 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="1feaf-108">그런 다음 추가 구성을 완료하고 파일럿 그룹이 전체 프로덕션에 도달할 때까지 파일럿 그룹을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="1feaf-109">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1feaf-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="1feaf-110">Id에 대한 Defender에는 추가 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="1feaf-111">필요한 라이선스를 구입하고 모든 Active Directory 도메인 컨트롤러 및 AD FS(Active Directory Federation Services) 서버에 센서를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="1feaf-112">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1feaf-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="1feaf-113">MDO를 평가하거나 파일럿한 후 전체 프로덕션 환경으로 승격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="1feaf-114">필요한 라이선스를 구매하여 프로비전하고 프로덕션 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="1feaf-115">프로덕션 전자 메일 도메인 또는 특정 사용자 그룹에 대해 권장 기준 정책 구성(Standard 또는 Strict)을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="1feaf-116">원하는 경우 프로덕션 전자 메일 도메인 또는 사용자 그룹에 대해 사용자 지정 MDO 정책을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="1feaf-117">그러나 할당된 모든 기준 정책은 항상 사용자 지정 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="1feaf-118">EOP로 직접 확인하려면 프로덕션 전자 메일 도메인의 공용 MX 레코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="1feaf-119">타사 SMTP 게이트웨이를 해제하고 이 릴레이와 연결된 모든 EXO 커넥터를 사용하지 않도록 설정하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="1feaf-120">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1feaf-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="1feaf-121">파일럿에서 프로덕션 환경으로의 Microsoft Defender 평가 환경을 승격하기 위해 지원되는 도구 및 방법을 사용하여 서비스에 더 많은 끝점을 [온보딩하기만 합니다.](/defender-endpoint/onboard-configure)</span><span class="sxs-lookup"><span data-stu-id="1feaf-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="1feaf-122">다음 일반 지침을 사용하여 끝점용 Microsoft Defender에 더 많은 장치를 온보딩합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="1feaf-123">장치가 최소 요구 사항을 [충족하는지 확인합니다.](/defender-endpoint/minimum-requirements)</span><span class="sxs-lookup"><span data-stu-id="1feaf-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="1feaf-124">장치에 따라 끝점 포털용 Defender의 온보딩 섹션에 제공된 구성 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="1feaf-125">장치에 적합한 관리 도구 및 배포 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="1feaf-126">검색 테스트를 실행하여 장치가 제대로 온보드 및 서비스에 보고되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="1feaf-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1feaf-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="1feaf-128">Microsoft Cloud App Security 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="1feaf-129">필요한 라이선스를 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="1feaf-130">특정 사용자 그룹에 대한 배포 범위를 지정한 경우 프로덕션 규모에 도달할 때까지 이러한 그룹의 범위를 늘리면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1feaf-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

