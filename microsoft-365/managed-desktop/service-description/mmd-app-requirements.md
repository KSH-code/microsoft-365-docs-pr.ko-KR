---
title: Microsoft Managed Desktop 앱 요구 사항
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659717"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="a6b40-103">Microsoft Managed Desktop 앱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6b40-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="a6b40-104">Microsoft Managed Desktop 장치의 성능, 안정성 및 서비스성을 보장하기 위해 특정 접근 방식을 사용하여 장치를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b40-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="a6b40-105">관리 영역</span><span class="sxs-lookup"><span data-stu-id="a6b40-105">Management area</span></span>  |<span data-ttu-id="a6b40-106">Microsoft Managed Desktop 방법</span><span class="sxs-lookup"><span data-stu-id="a6b40-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="a6b40-107">장치 구성 또는 정책 관리</span><span class="sxs-lookup"><span data-stu-id="a6b40-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="a6b40-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a6b40-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="a6b40-109">응용 프로그램 관리 </span><span class="sxs-lookup"><span data-stu-id="a6b40-109">Application management</span></span>     | <span data-ttu-id="a6b40-110">Microsoft Intune 회사 포털</span><span class="sxs-lookup"><span data-stu-id="a6b40-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="a6b40-111">드라이버 배포</span><span class="sxs-lookup"><span data-stu-id="a6b40-111">Driver deployment</span></span>     |  <span data-ttu-id="a6b40-112">장치, Windows 또는 Intune에 포함된 드라이버</span><span class="sxs-lookup"><span data-stu-id="a6b40-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="a6b40-113">장치 보안</span><span class="sxs-lookup"><span data-stu-id="a6b40-113">Device security</span></span>     | <span data-ttu-id="a6b40-114">장치 [보안 참조](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="a6b40-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="a6b40-115">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="a6b40-115">Identity and access management</span></span>     | <span data-ttu-id="a6b40-116">ID [및 액세스 관리 참조](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="a6b40-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="a6b40-117">네트워크 보안</span><span class="sxs-lookup"><span data-stu-id="a6b40-117">Network security</span></span>     | <span data-ttu-id="a6b40-118">네트워크 [보안 참조](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="a6b40-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="a6b40-119">정보 보안</span><span class="sxs-lookup"><span data-stu-id="a6b40-119">Information security</span></span>     |  <span data-ttu-id="a6b40-120">정보 [보안 참조](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="a6b40-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="a6b40-121">데이터 복구</span><span class="sxs-lookup"><span data-stu-id="a6b40-121">Data recovery</span></span>     | <span data-ttu-id="a6b40-122">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="a6b40-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="a6b40-123">핵심 생산성</span><span class="sxs-lookup"><span data-stu-id="a6b40-123">Core productivity</span></span>     | <span data-ttu-id="a6b40-124">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="a6b40-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="a6b40-125">브라우저</span><span class="sxs-lookup"><span data-stu-id="a6b40-125">Browser</span></span>     | <span data-ttu-id="a6b40-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a6b40-126">Microsoft Edge</span></span>        |




<span data-ttu-id="a6b40-127">Microsoft Managed Desktop 장치에서 실행 중인 다른 소프트웨어를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b40-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="a6b40-128">장치 관리, 장치 보안, 성능 또는 안정성에 부정적인 영향을 미치는 경우 서비스 계획에 대한 예외를 요청해야 할 [수 있습니다.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="a6b40-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
