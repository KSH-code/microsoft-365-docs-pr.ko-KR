---
title: 기존 인프라를 사용하여 Microsoft 365 Enterprise 배포
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 기존 인프라가 있는 경우 Microsoft 365 Enterprise 배포에 대한 종료 조건을 안내합니다.
ms.openlocfilehash: 1b464398b981133e2851760d7bfe16869f1d1429
ms.sourcegitcommit: 328b31f69663669b3c656b2e4db529f70d1c753e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "37148512"
---
# <a name="deployment-of-microsoft-365-enterprise-with-existing-infrastructure"></a><span data-ttu-id="80f73-103">기존 인프라를 사용하여 Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="80f73-103">Deployment of Microsoft 365 Enterprise with existing infrastructure</span></span>

<span data-ttu-id="80f73-p101">대부분의 조직에는 기존 네트워킹, ID 및 기타 구성 요소 또는 Microsoft 온-프레미스 제품 및 클라우드 기반 서비스가 있습니다. 이 문서에서는 기존 인프라를 조정하거나 변경하는 방법을 신속하게 확인할 수 있도록 Microsoft 365 Enterprise 배포의 각 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="80f73-p101">Many organizations have exisiting networking, identity, and other components or Microsoft on-premises products and cloud-based services. This article steps through each phase of the deployment of Microsoft 365 Enterprise so you can quickly determine how to adapt or change your existing infrastructure.</span></span>

<span data-ttu-id="80f73-p102">각 단계를 종료하려면 먼저 반드시 충족해야 하는 필수 조건과 고려할 선택적 조건의 집합인 종료 조건을 검사해야 합니다. 각 단계의 종료 조건은 온-프레미스 및 클라우드 인프라와 결과적인 종단 간 구성이 Microsoft 365 Enterprise 배포에 대한 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80f73-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meets the requirements for a Microsoft 365 Enterprise deployment.</span></span>

> [!Note] 
> <span data-ttu-id="80f73-p103">FastTrack은 사용자가 원하는 일정에 따라 클라우드로 전환할 수 있도록 Microsoft 엔지니어가 제공하는 지속적이고 반복 가능한 혜택입니다(구독의 일부로 무료로 제공). 또한 FastTrack은 필요에 따라 적격 파트너에게 추가 서비스에 대한 액세스를 제공합니다. 지금까지 40,000여 명의 고객을 보유한 FastTrack은 조직 전체에서 ROI를 극대화하고, 배포를 가속화하고, 도입을 늘리도록 도와줍니다. [Microsoft 365용 FastTrack](https://fasttrack.microsoft.com/microsoft365)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80f73-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

## <a name="exit-criteria-for-networking-phase-1"></a><span data-ttu-id="80f73-112">네트워킹에 대한 종료 조건(1단계)</span><span class="sxs-lookup"><span data-stu-id="80f73-112">Exit criteria for networking (phase 1)</span></span>

<span data-ttu-id="80f73-113">네트워킹 인프라에 대한 다음과 같은 필수 및 선택적 조건을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="80f73-113">Step through the following required and optional conditions for the networking infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for networking](./includes/deployment-exit-criteria-networking.md)]

## <a name="exit-criteria-for-identity-phase-2"></a><span data-ttu-id="80f73-114">ID에 대한 종료 조건(2단계)</span><span class="sxs-lookup"><span data-stu-id="80f73-114">Exit criteria for identity (phase 2)</span></span>

<span data-ttu-id="80f73-115">ID 인프라에 대한 다음과 같은 필수 및 선택적 조건을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="80f73-115">Step through the following required and optional conditions for the identity infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-identity.md)]

## <a name="exit-criteria-for-windows-10-enterprise-phase-3"></a><span data-ttu-id="80f73-116">Windows 10 Enterprise에 대한 종료 조건(3단계)</span><span class="sxs-lookup"><span data-stu-id="80f73-116">Exit criteria for Windows 10 Enterprise (phase 3)</span></span>

<span data-ttu-id="80f73-117">Windows 10 Enterprise 인프라에 대한 다음과 같은 필수 및 선택적 조건을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="80f73-117">Step through the following required and optional conditions for the Windows 10 Enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-windows10.md)]

## <a name="exit-criteria-for-office-365-proplus-phase-4"></a><span data-ttu-id="80f73-118">Office 365 ProPlus에 대한 종료 조건(4단계)</span><span class="sxs-lookup"><span data-stu-id="80f73-118">Exit criteria for Office 365 ProPlus (phase 4)</span></span>

<span data-ttu-id="80f73-119">Office 365 ProPlus 인프라의 평가, 배포 계획, 배포에 대한 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="80f73-119">Meet the requirements for assessment, deployment planning, and deployment of the Office 365 ProPlus infrastructure for Microsoft 365 Enterprise.</span></span>

[!INCLUDE [Deployment exit criteria for Office 365 ProPlus](./includes/deployment-exit-criteria-office365proplus.md)]

## <a name="exit-criteria-for-mobile-device-management-phase-5"></a><span data-ttu-id="80f73-120">모바일 장치 관리에 대한 종료 조건(5단계)</span><span class="sxs-lookup"><span data-stu-id="80f73-120">Exit criteria for mobile device management (phase 5)</span></span>

<span data-ttu-id="80f73-121">모바일 장치 관리 인프라에 대한 다음 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="80f73-121">Meet the following requirements for the mobile device management infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for mobile device management](./includes/deployment-exit-criteria-mobility.md)]

## <a name="exit-criteria-for-information-protection-phase-6"></a><span data-ttu-id="80f73-122">정보 보호에 대한 종료 조건(6단계)</span><span class="sxs-lookup"><span data-stu-id="80f73-122">Exit criteria for information protection (phase 6)</span></span>

<span data-ttu-id="80f73-123">정보 보호 인프라에 대한 다음과 같은 필수 및 선택적 조건을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="80f73-123">Step through the following required and optional conditions for the information protection infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for information protection](./includes/deployment-exit-criteria-infoprotect.md)]

