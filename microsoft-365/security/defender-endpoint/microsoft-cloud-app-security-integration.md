---
title: Microsoft Cloud App Security 통합 개요
ms.reviewer: ''
description: 끝점용 Microsoft Defender는 모든 클라우드 앱 네트워킹 활동을 전달하여 Cloud App Security와 통합됩니다.
keywords: 클라우드, 앱, 네트워킹, 가시성, 사용
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
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: d756c738f9f61638a9e7424aa3fdf639f8f02f2a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185602"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="f6b2d-104">Endpoint용 Defender의 Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="f6b2d-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f6b2d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f6b2d-105">**Applies to:**</span></span>
- [<span data-ttu-id="f6b2d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f6b2d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f6b2d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6b2d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f6b2d-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f6b2d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6b2d-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f6b2d-110">Microsoft Cloud App Security(Cloud App Security)는 클라우드에 저장된 데이터에 대한 규정 준수 요구 사항을 적용하면서 클라우드 앱에 대한 액세스를 제어하고 제한할 수 있도록 하여 클라우드 앱 및 서비스에 대한 가시성을 제공하는 포괄적인 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="f6b2d-111">자세한 내용은 [Cloud App Security를 참조하세요.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="f6b2d-111">For more information, see [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="f6b2d-112">이 기능은 Windows 10 버전 1809 이상을 실행하는 장치에서 [Enterprise Mobility + Security용](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) E5 라이선스와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="f6b2d-113">Endpoint용 Microsoft Defender 및 Cloud App Security 통합</span><span class="sxs-lookup"><span data-stu-id="f6b2d-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="f6b2d-114">Cloud App Security 검색은 엔터프라이즈 방화벽 및 프록시 서버에서 클라우드 트래픽 로그로 전달되는 로그를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="f6b2d-115">끝점용 Microsoft Defender는 모든 클라우드 앱 네트워킹 활동을 수집 및 전달하여 Cloud App Security와 통합하여 클라우드 앱 사용에 대해 최고의 가시성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="f6b2d-116">모니터링 기능은 장치에 기본 제공되어 네트워크 활동에 대한 전체 범위를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="f6b2d-117">통합을 통해 기존 Cloud App Security 검색에 다음과 같은 주요 개선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="f6b2d-118">모든 곳에서 사용 가능 - 네트워크 활동은 끝점에서 직접 수집하기 때문에 엔터프라이즈 방화벽 또는 프록시 서버를 통해 라우팅되는 트래픽에 더 이상 종속되지 않고 장치가 회사 네트워크의 설정 또는 해제된 모든 곳에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="f6b2d-119">구성이 필요 없는 기본 제공 작업 - 클라우드 트래픽 로그를 Cloud App Security로 전달하려면 방화벽 및 프록시 서버 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="f6b2d-120">Endpoint용 Defender 및 Cloud App Security 통합에서는 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="f6b2d-121">Microsoft Defender 보안 센터 설정에서 켜기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="f6b2d-122">디바이스 컨텍스트 - 클라우드 트래픽 로그에 장치 컨텍스트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="f6b2d-123">끝점 네트워크 활동에 대한 Defender는 장치 컨텍스트(클라우드 앱에 액세스한 장치)로 보고됩니다. 따라서 네트워크 활동이 수행된(사용자) 외에 네트워크 활동이 수행된 위치를 정확하게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="f6b2d-124">클라우드 검색에 대한 자세한 내용은 검색된 앱 [작업을 참조하세요.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="f6b2d-124">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="f6b2d-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f6b2d-125">Related topic</span></span>

- [<span data-ttu-id="f6b2d-126">Microsoft Cloud App Security 통합 구성</span><span class="sxs-lookup"><span data-stu-id="f6b2d-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
