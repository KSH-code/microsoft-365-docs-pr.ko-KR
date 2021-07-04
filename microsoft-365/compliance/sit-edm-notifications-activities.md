---
title: 정확한 데이터 일치 활동에 대한 알림 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 일치 활동에 대한 알림을 만드는 방법을 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: da00c43ae9ba5b129129027df16f49ef80b8757d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288170"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="bedf8-103">정확한 데이터 일치 활동에 대한 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="bedf8-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="bedf8-104">[EDM(정확한 데이터 일치)을 사용하여 중요한 사용자 지정 정보 유형을 만들면](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) [감사 로그](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log)에 여러 활동이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bedf8-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="bedf8-105">[New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet를 사용하여 이러한 활동이 발생할 때 알려주는 알림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf8-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="bedf8-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="bedf8-106">CreateSchema</span></span>
- <span data-ttu-id="bedf8-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="bedf8-107">EditSchema</span></span>
- <span data-ttu-id="bedf8-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="bedf8-108">RemoveSchema</span></span>
- <span data-ttu-id="bedf8-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="bedf8-109">UploadDataFailed</span></span>
- <span data-ttu-id="bedf8-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="bedf8-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="bedf8-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="bedf8-111">Pre-requisites</span></span>

<span data-ttu-id="bedf8-112">사용하는 계정이 다음 중 하나에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf8-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="bedf8-113">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="bedf8-113">a global admin</span></span>
- <span data-ttu-id="bedf8-114">규정 준수 관리자</span><span class="sxs-lookup"><span data-stu-id="bedf8-114">compliance administrator</span></span>
- <span data-ttu-id="bedf8-115">Exchange Online 관리자</span><span class="sxs-lookup"><span data-stu-id="bedf8-115">Exchange Online administrator</span></span>

<span data-ttu-id="bedf8-116">DLP 권한에 관한 자세한 내용은 [권한](data-loss-prevention-policies.md#permissions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bedf8-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="bedf8-117">EDM 기반 분류가 이 구독에 포함되어 있습니다</span><span class="sxs-lookup"><span data-stu-id="bedf8-117">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="bedf8-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="bedf8-118">Office 365 E5</span></span>
- <span data-ttu-id="bedf8-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bedf8-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="bedf8-120">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="bedf8-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="bedf8-121">Microsoft E5/A5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="bedf8-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="bedf8-122">DLP 라이선싱에 대한 자세한 내용은 [보안 & 준수에 대한 Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bedf8-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="bedf8-123">EDM 활동에 대한 알림 구성</span><span class="sxs-lookup"><span data-stu-id="bedf8-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="bedf8-124">[보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)에 연결</span><span class="sxs-lookup"><span data-stu-id="bedf8-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)</span></span> 

2. <span data-ttu-id="bedf8-125">알림을 생성하려는 작업을 사용하여 `New-ProtectionAlert`cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf8-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="bedf8-126">예를 들어 **UploadDataCompleted** 작업이 발생했을 때 알림을 받으려면 를 다음을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="bedf8-126">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="bedf8-127">**UploadDataFailed** 에 대해 다음을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bedf8-127">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="bedf8-128">관련 문서</span><span class="sxs-lookup"><span data-stu-id="bedf8-128">Related articles</span></span>

- [<span data-ttu-id="bedf8-129">정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기(EDM)</span><span class="sxs-lookup"><span data-stu-id="bedf8-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="bedf8-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="bedf8-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert)