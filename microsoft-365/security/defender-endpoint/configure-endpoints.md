---
title: Windows 10 장치용 온보딩 도구 및 방법
description: 끝점 Windows 10 센서로 센서 데이터를 보낼 수 있도록 장치 온보딩
keywords: 온보딩 Windows 10 장치, 그룹 정책, 끝점 구성 관리자, 모바일 장치 관리, 로컬 스크립트, gp, sccm, mdm, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892832"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="e0c33-104">Windows 10 장치용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="e0c33-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e0c33-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e0c33-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0c33-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e0c33-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e0c33-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0c33-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="e0c33-108">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="e0c33-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="e0c33-109">Microsoft 365 내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="e0c33-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="e0c33-110">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e0c33-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0c33-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="e0c33-112">끝점용 Defender 서비스가 해당 장치에서 센서 데이터를 얻을 수 있도록 조직의 장치를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="e0c33-113">조직에서 장치를 구성하는 데 사용할 수 있는 다양한 방법 및 배포 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="e0c33-114">다음과 같은 배포 도구 및 방법이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="e0c33-115">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="e0c33-115">Group Policy</span></span>
- <span data-ttu-id="e0c33-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e0c33-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="e0c33-117">모바일 장치 관리(Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="e0c33-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="e0c33-118">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="e0c33-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e0c33-119">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e0c33-119">In this section</span></span>
<span data-ttu-id="e0c33-120">항목</span><span class="sxs-lookup"><span data-stu-id="e0c33-120">Topic</span></span> | <span data-ttu-id="e0c33-121">설명</span><span class="sxs-lookup"><span data-stu-id="e0c33-121">Description</span></span>
:---|:---
[<span data-ttu-id="e0c33-122">그룹 정책을 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="e0c33-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="e0c33-123">그룹 정책을 사용하여 디바이스에 구성 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="e0c33-124">Windows 사용하여 장치 온보드 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e0c33-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="e0c33-125">Microsoft Endpoint Manager(현재 분기) 버전 1606 또는 Microsoft Endpoint Manager(현재 분기) 버전 1602 이전 버전을 사용하여 디바이스에 구성 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="e0c33-126">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="e0c33-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="e0c33-127">모바일 장치 관리 도구 또는 Microsoft Intune 구성 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="e0c33-128">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="e0c33-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="e0c33-129">로컬 스크립트를 사용하여 끝점에서 구성 패키지를 배포하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="e0c33-130">비영구 VDI(가상 데스크톱 인프라) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="e0c33-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="e0c33-131">구성 패키지를 사용하여 VDI 디바이스를 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="e0c33-132">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e0c33-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0c33-133">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c33-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
