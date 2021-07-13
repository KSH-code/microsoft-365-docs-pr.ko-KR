---
title: 기준을 사용하여 표준 테넌트 구성 배포 개요
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 서비스 공급자를 사용하는 MSP(관리 Microsoft 365 Lighthouse)의 경우 기준을 사용하여 표준 테넌트 구성을 배포하는 방법을 배워야 합니다.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409186"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="901f9-103">기준을 사용하여 표준 테넌트 구성 배포 개요</span><span class="sxs-lookup"><span data-stu-id="901f9-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="901f9-104">이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="901f9-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="901f9-105">조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="901f9-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="901f9-106">Microsoft 365 Lighthouse 기준은 여러 테넌트에서 보안 설정을 평가하고 Microsoft 365 수 있는 반복 가능하고 확장 가능한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="901f9-107">또한 기준은 사용자, 장치 및 데이터를 보호하는 구성을 사용하여 핵심 보안 정책 및 테넌트 준수 표준을 모니터링하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="901f9-108">파트너가 자신의 속도에 따라 보안을 채택할 수 있도록 설계된 Microsoft 365 Lighthouse 표준 기준 매개 변수 집합과 Microsoft 365 서비스를 위한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="901f9-109">이러한 보안 구성은 테넌트의 보안 및 준수 Microsoft 365 측정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="901f9-110">기본 기준 및 해당 배포 단계는 기본 기본 계획 내에서 볼 수 Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="901f9-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="901f9-111">테넌트에 기준을 적용하려면  왼쪽 탐색 창에서 테넌트를 선택한 다음 테넌트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="901f9-112">그런 다음 배포 계획 **탭으로 이동하여** 원하는 기준을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="901f9-113">표준 기준 보안 템플릿</span><span class="sxs-lookup"><span data-stu-id="901f9-113">Standard baseline security templates</span></span>

<span data-ttu-id="901f9-114">Microsoft 365 Lighthouse 표준 기준 구성은 모든 관리되는 테넌트가 허용되는 보안 범위 및 규정 준수 상태를 달성할 수 있도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="901f9-115">다음 표의 기준 구성은 기본 Microsoft 365 Lighthouse 표준으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="901f9-116">기준 구성</span><span class="sxs-lookup"><span data-stu-id="901f9-116">Baseline configuration</span></span> | <span data-ttu-id="901f9-117">설명</span><span class="sxs-lookup"><span data-stu-id="901f9-117">Description</span></span> |
|--|--|
| <span data-ttu-id="901f9-118">관리자에게 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="901f9-118">Require MFA for admins</span></span> | <span data-ttu-id="901f9-119">관리자에 대해 다단계 인증을 요구하는 보고서 전용 조건부 액세스 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="901f9-120">모든 클라우드 응용 프로그램에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="901f9-121">최종 사용자에 대해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="901f9-121">Require MFA for end users</span></span> | <span data-ttu-id="901f9-122">사용자에 대해 다단계 인증이 필요한 보고서 전용 조건부 액세스 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="901f9-123">모든 클라우드 응용 프로그램에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="901f9-124">레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="901f9-124">Block legacy authentication</span></span> | <span data-ttu-id="901f9-125">레거시 클라이언트 인증을 차단하는 보고서 전용 조건부 액세스 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="901f9-126">디바이스를 Microsoft Endpoint Manager – Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="901f9-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="901f9-127">테넌트 장치가 테넌트에 등록할 수 있도록 장치 등록을 Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="901f9-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="901f9-128">이 수행은 사용자와 사용자 간에 자동 등록을 설정하여 Azure Active Directory Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="901f9-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="901f9-129">AV(바이러스 백신) 정책 구성</span><span class="sxs-lookup"><span data-stu-id="901f9-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="901f9-130">미리 구성된 Windows 장치용 장치 구성 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="901f9-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="901f9-131">창 10 준수 정책 설정</span><span class="sxs-lookup"><span data-stu-id="901f9-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="901f9-132">기본 Windows 충족하기 위해 미리 구성된 설정이 있는 장치 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="901f9-133">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="901f9-133">Related content</span></span>

<span data-ttu-id="901f9-134">[기본 Microsoft 365 Lighthouse](m365-lighthouse-deploy-baselines.md) 배포(문서)</span><span class="sxs-lookup"><span data-stu-id="901f9-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)</span></span>\
<span data-ttu-id="901f9-135">[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="901f9-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
