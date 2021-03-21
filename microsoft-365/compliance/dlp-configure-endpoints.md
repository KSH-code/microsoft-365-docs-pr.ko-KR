---
title: Windows 10 장치용 온보딩 도구 및 방법
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
description: 센서 데이터를 Microsoft 365 규정 준수 솔루션으로 보낼 수 있도록 Windows 10 디바이스 온보드
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917854"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="b5820-103">Windows 10 장치용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="b5820-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="b5820-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b5820-104">**Applies to:**</span></span>
- [<span data-ttu-id="b5820-105">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="b5820-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="b5820-106">Microsoft 365 끝점 데이터 손실 방지 서비스가 해당 장치에서 센서 데이터를 얻을 수 있도록 조직의 장치를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5820-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="b5820-107">조직에서 장치를 구성하는 데 사용할 수 있는 다양한 방법 및 배포 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5820-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="b5820-108">다음과 같은 배포 도구 및 방법이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5820-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="b5820-109">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="b5820-109">group policy</span></span>
- <span data-ttu-id="b5820-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b5820-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="b5820-111">모바일 장치 관리(Microsoft Intune 포함)</span><span class="sxs-lookup"><span data-stu-id="b5820-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="b5820-112">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="b5820-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b5820-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b5820-113">In this section</span></span>
<span data-ttu-id="b5820-114">항목</span><span class="sxs-lookup"><span data-stu-id="b5820-114">Topic</span></span> | <span data-ttu-id="b5820-115">설명</span><span class="sxs-lookup"><span data-stu-id="b5820-115">Description</span></span>
:---|:---
[<span data-ttu-id="b5820-116">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="b5820-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="b5820-117">그룹 정책을 사용하여 디바이스에 구성 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="b5820-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="b5820-118">Microsoft Endpoint Configuration Manager를 사용하여 Windows 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="b5820-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="b5820-119">Microsoft Endpoint Configuration Manager(현재 분기) 버전 1606 또는 Microsoft Endpoint Configuration Manager(현재 분기) 버전 1602 이전 버전을 사용하여 디바이스에 구성 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5820-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="b5820-120">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="b5820-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="b5820-121">모바일 장치 관리 도구 또는 Microsoft Intune을 사용하여 디바이스에 구성 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="b5820-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="b5820-122">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="b5820-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="b5820-123">로컬 스크립트를 사용하여 끝점에서 구성 패키지를 배포하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="b5820-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="b5820-124">비영구 가상 데스크톱 인프라(VDI) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="b5820-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="b5820-125">구성 패키지를 사용하여 VDI 디바이스를 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="b5820-125">Learn how to use the configuration package to configure VDI devices.</span></span>