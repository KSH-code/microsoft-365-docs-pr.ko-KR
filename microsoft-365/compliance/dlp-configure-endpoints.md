---
title: Windows 10 장치에 대 한 온 보 딩 도구 및 방법 (미리 보기)
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
description: Microsoft 365 준수 솔루션에 센서 데이터를 보낼 수 있도록 Windows 10 장치를 온보드
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769645"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="ed8d9-103">Windows 10 장치에 대 한 온 보 딩 도구 및 방법 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ed8d9-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="ed8d9-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ed8d9-104">**Applies to:**</span></span>
- [<span data-ttu-id="ed8d9-105">Microsoft 365 Endpoint data 손실 방지 (DLP)</span><span class="sxs-lookup"><span data-stu-id="ed8d9-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="ed8d9-106">Microsoft 365 끝점 데이터 손실 방지 서비스가 센서 데이터를 가져올 수 있도록 조직의 장치를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d9-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="ed8d9-107">조직에서 장치를 구성 하는 데 사용할 수 있는 다양 한 방법과 배포 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d9-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="ed8d9-108">다음과 같은 배포 도구 및 메서드가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d9-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="ed8d9-109">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="ed8d9-109">group policy</span></span>
- <span data-ttu-id="ed8d9-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ed8d9-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="ed8d9-111">모바일 장치 관리 (Microsoft Intune 포함)</span><span class="sxs-lookup"><span data-stu-id="ed8d9-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="ed8d9-112">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="ed8d9-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ed8d9-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ed8d9-113">In this section</span></span>
<span data-ttu-id="ed8d9-114">항목</span><span class="sxs-lookup"><span data-stu-id="ed8d9-114">Topic</span></span> | <span data-ttu-id="ed8d9-115">설명</span><span class="sxs-lookup"><span data-stu-id="ed8d9-115">Description</span></span>
:---|:---
[<span data-ttu-id="ed8d9-116">그룹 정책을 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="ed8d9-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="ed8d9-117">그룹 정책을 사용 하 여 장치에 구성 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d9-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="ed8d9-118">Microsoft Endpoint Configuration Manager를 사용 하는 온보드 Windows 장치</span><span class="sxs-lookup"><span data-stu-id="ed8d9-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="ed8d9-119">Microsoft Endpoint Configuration Manager (현재 분기) 버전 1606 또는 Microsoft Endpoint Configuration Manager (현재 분기) 버전 1602 또는 이전을 사용 하 여 장치에 구성 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d9-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="ed8d9-120">모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="ed8d9-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="ed8d9-121">모바일 장치 관리 도구 또는 Microsoft Intune을 사용 하 여 장치에 구성 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d9-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="ed8d9-122">로컬 스크립트를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="ed8d9-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="ed8d9-123">로컬 스크립트를 사용 하 여 끝점에 구성 패키지를 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d9-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="ed8d9-124">온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)</span><span class="sxs-lookup"><span data-stu-id="ed8d9-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="ed8d9-125">구성 패키지를 사용 하 여 VDI 장치를 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d9-125">Learn how to use the configuration package to configure VDI devices.</span></span>
