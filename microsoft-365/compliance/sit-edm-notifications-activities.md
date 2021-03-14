---
title: 정확한 데이터 일치 활동에 대한 알림 만들기(미리 보기)
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
ms.openlocfilehash: a537cffe253fa20cf6838ddf3fd9a51ec440fe76
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766700"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="50fc6-103">정확한 데이터 일치 활동에 대한 알림 만들기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="50fc6-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="50fc6-104">[EDM(정확한 데이터 일치)을 사용하여 중요한 사용자 지정 정보 유형을 만들면](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) [감사 로그](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log)에 여러 활동이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="50fc6-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="50fc6-105">[New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet를 사용하여 이러한 활동이 발생할 때 알려주는 알림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="50fc6-105">You can use the [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="50fc6-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="50fc6-106">CreateSchema</span></span>
- <span data-ttu-id="50fc6-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="50fc6-107">EditSchema</span></span>
- <span data-ttu-id="50fc6-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="50fc6-108">RemoveSchema</span></span>
- <span data-ttu-id="50fc6-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="50fc6-109">UploadDataFailed</span></span>
- <span data-ttu-id="50fc6-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="50fc6-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="50fc6-111">EDM 활동에 대한 알림을 생성하는 기능은 World Wide 및 GCC 클라우드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fc6-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="50fc6-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="50fc6-112">Pre-requisites</span></span>

<span data-ttu-id="50fc6-113">사용하는 계정이 다음 중 하나에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50fc6-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="50fc6-114">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="50fc6-114">a global admin</span></span>
- <span data-ttu-id="50fc6-115">규정 준수 관리자</span><span class="sxs-lookup"><span data-stu-id="50fc6-115">compliance administrator</span></span>
- <span data-ttu-id="50fc6-116">Exchange Online 관리자</span><span class="sxs-lookup"><span data-stu-id="50fc6-116">Exchange Online administrator</span></span>

<span data-ttu-id="50fc6-117">DLP 권한에 관한 자세한 내용은 [권한](data-loss-prevention-policies.md#permissions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50fc6-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="50fc6-118">EDM 기반 분류가 이 구독에 포함되어 있습니다</span><span class="sxs-lookup"><span data-stu-id="50fc6-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="50fc6-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="50fc6-119">Office 365 E5</span></span>
- <span data-ttu-id="50fc6-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="50fc6-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="50fc6-121">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="50fc6-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="50fc6-122">Microsoft E5/A5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="50fc6-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="50fc6-123">DLP 라이선싱에 대한 자세한 내용은 [보안 & 준수에 대한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50fc6-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="50fc6-124">EDM 활동에 대한 알림 구성</span><span class="sxs-lookup"><span data-stu-id="50fc6-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="50fc6-125">[보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)에 연결</span><span class="sxs-lookup"><span data-stu-id="50fc6-125">Connect to the [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="50fc6-126">알림을 생성하려는 작업을 사용하여 `New-ProtectionAlert`cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="50fc6-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="50fc6-127">예를 들어 **UploadDataCompleted** 작업이 발생했을 때 알림을 받으려면 를 다음을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="50fc6-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="50fc6-128">**UploadDataFailed** 에 대해 다음을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fc6-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="50fc6-129">관련 문서</span><span class="sxs-lookup"><span data-stu-id="50fc6-129">Related articles</span></span>

- [<span data-ttu-id="50fc6-130">정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기(EDM)</span><span class="sxs-lookup"><span data-stu-id="50fc6-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="50fc6-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="50fc6-131">New-ProtectionAlert</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) 