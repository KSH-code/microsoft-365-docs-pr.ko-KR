---
title: 장치용 온보드 Windows 10 도구
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 센서 데이터를 Windows 10 준수 솔루션으로 보낼 수 있도록 장치 온보드 Microsoft 365 있습니다.
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341703"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="0579e-103">Windows 10 장치용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="0579e-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="0579e-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0579e-104">**Applies to:**</span></span>
- [<span data-ttu-id="0579e-105">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="0579e-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="0579e-106">조직의 장치는 끝점 데이터 손실 방지 서비스가 센서 데이터를 Microsoft 365 수 있도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0579e-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="0579e-107">조직에서 장치를 구성하는 데 사용할 수 있는 다양한 방법 및 배포 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0579e-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="0579e-108">다음과 같은 배포 도구 및 방법이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0579e-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="0579e-109">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="0579e-109">group policy</span></span>
- <span data-ttu-id="0579e-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0579e-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="0579e-111">모바일 장치 관리(Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="0579e-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="0579e-112">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="0579e-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0579e-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="0579e-113">In this section</span></span>
<span data-ttu-id="0579e-114">항목</span><span class="sxs-lookup"><span data-stu-id="0579e-114">Topic</span></span> | <span data-ttu-id="0579e-115">설명</span><span class="sxs-lookup"><span data-stu-id="0579e-115">Description</span></span>
:---|:---
[<span data-ttu-id="0579e-116">그룹 정책을 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="0579e-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="0579e-117">그룹 정책을 사용하여 디바이스에 구성 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="0579e-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="0579e-118">Windows 사용하여 장치 온보드 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0579e-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="0579e-119">Microsoft Endpoint Configuration Manager(현재 분기) 버전 1606 또는 Microsoft Endpoint Configuration Manager(현재 분기) 버전 1602 이전 버전을 사용하여 디바이스에 구성 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0579e-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="0579e-120">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="0579e-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="0579e-121">모바일 장치 관리 도구 또는 Microsoft Intune 구성 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0579e-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="0579e-122">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="0579e-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="0579e-123">로컬 스크립트를 사용하여 끝점에서 구성 패키지를 배포하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="0579e-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="0579e-124">비영구 VDI(가상 데스크톱 인프라) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="0579e-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="0579e-125">구성 패키지를 사용하여 VDI 디바이스를 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="0579e-125">Learn how to use the configuration package to configure VDI devices.</span></span>