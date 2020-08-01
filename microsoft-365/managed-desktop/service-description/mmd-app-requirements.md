---
title: Microsoft Managed Desktop 응용 프로그램 요구 사항
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: bd775e201f5fec556941ae0e8e7b025744da0419
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529436"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="070c8-103">Microsoft Managed Desktop 응용 프로그램 요구 사항</span><span class="sxs-lookup"><span data-stu-id="070c8-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="070c8-104">Microsoft Managed Desktop에서는 장치에 대 한 성능, 안정성 및 서비스 편리성을 보장 하기 위해 특정 방법을 사용 하 여 장치를 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="070c8-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span> <span data-ttu-id="070c8-105">아래 영역에 대해 Microsoft Managed Desktop이 사용 하는 방식이 제대로 작동 하지 않는 경우에는 [서비스 계획에](customizing.md)대 한 예외를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="070c8-105">If you’re sure that the approach taken by Microsoft Managed Desktop for the areas below will not work for you, you can request an [exception to the service plan](customizing.md).</span></span>


|<span data-ttu-id="070c8-106">관리 영역</span><span class="sxs-lookup"><span data-stu-id="070c8-106">Management area</span></span>  |<span data-ttu-id="070c8-107">Microsoft Managed Desktop 접근 방식</span><span class="sxs-lookup"><span data-stu-id="070c8-107">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="070c8-108">장치 구성 또는 정책 관리</span><span class="sxs-lookup"><span data-stu-id="070c8-108">Device configuration or policy management</span></span>     |  <span data-ttu-id="070c8-109">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="070c8-109">Microsoft Intune</span></span>       |
|<span data-ttu-id="070c8-110">응용 프로그램 관리 </span><span class="sxs-lookup"><span data-stu-id="070c8-110">Application management</span></span>     | <span data-ttu-id="070c8-111">Microsoft Intune 및 회사 포털</span><span class="sxs-lookup"><span data-stu-id="070c8-111">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="070c8-112">드라이버 배포</span><span class="sxs-lookup"><span data-stu-id="070c8-112">Driver deployment</span></span>     |  <span data-ttu-id="070c8-113">장치, Windows Update 또는 Intune에 포함 되는 드라이버</span><span class="sxs-lookup"><span data-stu-id="070c8-113">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="070c8-114">장치 보안</span><span class="sxs-lookup"><span data-stu-id="070c8-114">Device security</span></span>     | <span data-ttu-id="070c8-115">[장치 보안](security.md#device-security) 참조</span><span class="sxs-lookup"><span data-stu-id="070c8-115">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="070c8-116">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="070c8-116">Identity and access management</span></span>     | <span data-ttu-id="070c8-117">[Id 및 액세스 관리](security.md#identity-and-access-management) 참조</span><span class="sxs-lookup"><span data-stu-id="070c8-117">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="070c8-118">네트워크 보안</span><span class="sxs-lookup"><span data-stu-id="070c8-118">Network security</span></span>     | <span data-ttu-id="070c8-119">[네트워크 보안](security.md#network-security) 참조</span><span class="sxs-lookup"><span data-stu-id="070c8-119">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="070c8-120">정보 보안</span><span class="sxs-lookup"><span data-stu-id="070c8-120">Information security</span></span>     |  <span data-ttu-id="070c8-121">[정보 보안](security.md#information-security) 참조</span><span class="sxs-lookup"><span data-stu-id="070c8-121">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="070c8-122">데이터 복구</span><span class="sxs-lookup"><span data-stu-id="070c8-122">Data recovery</span></span>     | <span data-ttu-id="070c8-123">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="070c8-123">OneDrive for Business</span></span>        |
|<span data-ttu-id="070c8-124">핵심 생산성</span><span class="sxs-lookup"><span data-stu-id="070c8-124">Core productivity</span></span>     | <span data-ttu-id="070c8-125">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="070c8-125">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="070c8-126">브라우저</span><span class="sxs-lookup"><span data-stu-id="070c8-126">Browser</span></span>     | <span data-ttu-id="070c8-127">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="070c8-127">Microsoft Edge</span></span>        |




<span data-ttu-id="070c8-128">Microsoft Managed Desktop은 관리 되는 장치에서 실행 되는 다른 소프트웨어를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="070c8-128">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="070c8-129">시스템 보안, 성능 또는 안정성에 부정적인 영향을 주는 경우 서비스 계획에 대 한 예외를 요청 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="070c8-129">If it negatively impacts system security, performance, or reliability, you might be required to request an exception to the service plan.</span></span>


