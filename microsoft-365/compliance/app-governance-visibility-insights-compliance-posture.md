---
title: 앱 규정 준수 상태 확인
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱 규정 준수 상태를 확인합니다.
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420252"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="2d6b8-103">앱 규정 준수 상태 확인</span><span class="sxs-lookup"><span data-stu-id="2d6b8-103">Determine your app compliance posture</span></span>

><span data-ttu-id="2d6b8-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="2d6b8-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="2d6b8-105">Microsoft 앱 거버넌스를 사용하면 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/appgovernance) 앱 거버넌스 개요 페이지에서 타사 앱의 규정 준수 상태와 Microsoft 365 테넌트에서의 데이터 액세스를 신속하게 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/appgovernance).</span></span>

![Microsoft 365 규정 준수 센터의 앱 거버넌스 개요 페이지](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="2d6b8-107">앱 거버넌스 데이터를 보려면 로그인 계정에 [관리자 역할](app-governance-get-started.md#administrator-roles) 중 하나가 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="2d6b8-108">이 페이지에서 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-108">From this page, you can see:</span></span>

- <span data-ttu-id="2d6b8-109">Microsoft Graph API를 사용하는 OAuth 지원 앱의 경우 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="2d6b8-110">사용자의 테넌트에 속한 수</span><span class="sxs-lookup"><span data-stu-id="2d6b8-110">How many are in your tenant</span></span>
  - <span data-ttu-id="2d6b8-111">과도한 권한을 갖은 수</span><span class="sxs-lookup"><span data-stu-id="2d6b8-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="2d6b8-112">높은 권한을 갖은 계정 수</span><span class="sxs-lookup"><span data-stu-id="2d6b8-112">How many are high privilege</span></span>

  <span data-ttu-id="2d6b8-113">이 정보를 통해 권한이 과도하게 부여된 높은 권한의 앱을 통해 조직에 대한 위험 수준을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="2d6b8-114">경고의 경우 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-114">For alerts:</span></span>

  - <span data-ttu-id="2d6b8-115">테넌트가 보유한 활성 경고 수</span><span class="sxs-lookup"><span data-stu-id="2d6b8-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="2d6b8-116">앱 거버넌스 검색(**위협 경고**)을 기반으로 하는 경고 수</span><span class="sxs-lookup"><span data-stu-id="2d6b8-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="2d6b8-117">적용된 앱 정책을 기반으로 하는 경고 수(**정책 경고**)</span><span class="sxs-lookup"><span data-stu-id="2d6b8-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="2d6b8-118">10개의 최신 경고</span><span class="sxs-lookup"><span data-stu-id="2d6b8-118">The 10 latest alerts</span></span>

  <span data-ttu-id="2d6b8-119">이 정보에서 경고가 생성되는 빈도와 검색된 경고 및 정책 기반 경고의 상대적 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="2d6b8-120">데이터 및 리소스 액세스의 경우 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-120">For data and resources access:</span></span>

  - <span data-ttu-id="2d6b8-121">지난 90일 동안의 애플리케이션 API 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="2d6b8-121">The application API data access in the last 90 days</span></span>
  - <span data-ttu-id="2d6b8-122">지난 90일 동안의 상위 리소스 사용량</span><span class="sxs-lookup"><span data-stu-id="2d6b8-122">The usage of the top resources in the last 90 days</span></span>

  <span data-ttu-id="2d6b8-123">이 정보에서 Microsoft 365 테넌트에서 데이터 액세스가 비정상적으로 급증했는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-123">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
