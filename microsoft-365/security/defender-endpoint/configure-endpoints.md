---
title: Windows 10 장치용 온보딩 도구 및 방법
description: 센서 데이터를 Microsoft Defender ATP 센서로 보낼 수 있도록 Windows 10 디바이스 온보딩
keywords: Windows 10 장치 온보딩, 그룹 정책, 끝점 구성 관리자, 모바일 장치 관리, 로컬 스크립트, gp, sccm, mdm, intune
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
ms.openlocfilehash: 77b843f9526d8b100845403bc8d2df4bf3259471
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760215"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="37829-104">Windows 10 장치용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="37829-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37829-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="37829-105">**Applies to:**</span></span>
- <span data-ttu-id="37829-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="37829-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="37829-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37829-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="37829-108">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="37829-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="37829-109">Microsoft 365 내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="37829-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="37829-110">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="37829-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37829-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="37829-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="37829-112">끝점용 Defender 서비스가 해당 장치에서 센서 데이터를 얻을 수 있도록 조직의 장치를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37829-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="37829-113">조직에서 장치를 구성하는 데 사용할 수 있는 다양한 방법 및 배포 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37829-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="37829-114">다음과 같은 배포 도구 및 방법이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="37829-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="37829-115">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="37829-115">Group Policy</span></span>
- <span data-ttu-id="37829-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="37829-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="37829-117">모바일 장치 관리(Microsoft Intune 포함)</span><span class="sxs-lookup"><span data-stu-id="37829-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="37829-118">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="37829-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="37829-119">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="37829-119">In this section</span></span>
<span data-ttu-id="37829-120">항목</span><span class="sxs-lookup"><span data-stu-id="37829-120">Topic</span></span> | <span data-ttu-id="37829-121">설명</span><span class="sxs-lookup"><span data-stu-id="37829-121">Description</span></span>
:---|:---
[<span data-ttu-id="37829-122">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="37829-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="37829-123">그룹 정책을 사용하여 디바이스에 구성 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="37829-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="37829-124">Microsoft Endpoint Configuration Manager를 사용하여 Windows 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="37829-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="37829-125">Microsoft Endpoint Manager(현재 분기) 버전 1606 또는 Microsoft Endpoint Manager(현재 분기) 버전 1602 또는 이전 버전을 사용하여 디바이스에 구성 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37829-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="37829-126">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="37829-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="37829-127">모바일 장치 관리 도구 또는 Microsoft Intune을 사용하여 디바이스에 구성 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="37829-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="37829-128">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="37829-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="37829-129">로컬 스크립트를 사용하여 끝점에서 구성 패키지를 배포하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="37829-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="37829-130">비영구 VDI(가상 데스크톱 인프라) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="37829-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="37829-131">구성 패키지를 사용하여 VDI 디바이스를 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="37829-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="37829-132">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="37829-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37829-133">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="37829-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
