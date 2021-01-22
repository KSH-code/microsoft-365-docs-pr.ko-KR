---
title: 앱 모니터링 & 보고 - 보안 센터
description: 조직에서 클라우드 앱 사용에 대한 더 많은 정보를 얻는 방법을 배워야 합니다. 다양한 종류의 앱, 위험 수준 및 경고를 포함합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, 앱
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930525"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="555c3-105">Microsoft 365 보안 센터의 앱 모니터링 및 보고</span><span class="sxs-lookup"><span data-stu-id="555c3-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="555c3-106">이러한 보고서는 조직에서 클라우드 앱이 사용되는 방식에 대한 더 많은 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="555c3-107">다양한 종류의 앱, 위험 수준 및 경고를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="555c3-108">위험 요소가 있는 이메일 계정 모니터링</span><span class="sxs-lookup"><span data-stu-id="555c3-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="555c3-109">**전자 메일 보호는** 전자 메일 계정을 위험에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="555c3-110">Microsoft Defender 보안 센터에서 추가로 조사할 계정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![전자 메일 보호 카드](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="555c3-112">사용자가 부여한 앱 권한 모니터링</span><span class="sxs-lookup"><span data-stu-id="555c3-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="555c3-113">**Cloud App Security - OAuth** 앱은 사용자가 사용 권한을 부여한 Cloud App Security에서 검색한 앱을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="555c3-114">Cloud App Security의 위험 카탈로그에는 70개가 넘는 위험 요인을 사용하여 평가된 16,000개가 넘는 앱이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="555c3-115">위험 요인은 앱 게시자와 같은 일반 정보에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="555c3-116">그런 다음 앱이 휴지 시 암호화를 지원하는지 또는 사용자 활동의 감사 로그를 제공하는지 여부와 같은 보안 조치 및 제어로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth 앱 카드](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="555c3-118">클라우드 앱 사용자 계정 모니터링</span><span class="sxs-lookup"><span data-stu-id="555c3-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="555c3-119">**주의가 필요할** 수 있는 검토 목록 계정에 대한 클라우드 앱 계정</span><span class="sxs-lookup"><span data-stu-id="555c3-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![검토 카드용 Cloud App 계정](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="555c3-121">사용되는 클라우드 앱 이해</span><span class="sxs-lookup"><span data-stu-id="555c3-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="555c3-122">**검색된 클라우드 앱(범주)은** 조직에서 사용되는 앱의 종류를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="555c3-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="555c3-123">Cloud App Security의 클라우드 검색 대시보드로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="555c3-124">자세한 내용은 [빠른 시작: 검색된 앱 사용.을 참조하세요.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="555c3-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![검색된 클라우드 앱 범주 카드](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="555c3-126">사용자가 클라우드 앱에 액세스하는 위치 모니터링</span><span class="sxs-lookup"><span data-stu-id="555c3-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="555c3-127">**클라우드 앱 활동 위치에는** 사용자가 클라우드 앱에 액세스하는 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Cloud App activity locations card](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="555c3-129">인프라 워크로드에 대한 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="555c3-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="555c3-130">**인프라 상태는** Azure Defender의 인프라 워크로드에 대한 상태 경고를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="555c3-131">Azure Defender는 Office 365에 대한 통합 보안 관리 및 Defender를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="555c3-132">방화벽 및 기타 파트너 솔루션을 포함하여 다양한 원본에서 보안 데이터를 수집, 검색 및 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c3-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="555c3-133">자세한 내용은 [Azure Defender 설명서를 참조하세요.](https://docs.microsoft.com/azure/security-center/)</span><span class="sxs-lookup"><span data-stu-id="555c3-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![인프라 상태 카드](../../media/infrastructure-health.png)
