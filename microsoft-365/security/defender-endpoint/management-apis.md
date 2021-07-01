---
title: 관리 및 API 개요
ms.reviewer: ''
description: 끝점용 Microsoft Defender의 관리 도구 및 API 범주에 대해 자세히 알아보시고
keywords: 등록, api, siem, rbac, 액세스, 포털, 통합, 조사, 응답, 엔터티, 엔터티, 사용자 컨텍스트, 응용 프로그램 컨텍스트, 스트리밍
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 471db75102eabd4d7fce14ec42d0a47562007aae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229986"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="22796-104">관리 및 API 개요</span><span class="sxs-lookup"><span data-stu-id="22796-104">Overview of management and APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22796-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="22796-105">**Applies to:**</span></span>
- [<span data-ttu-id="22796-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22796-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22796-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22796-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="22796-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="22796-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="22796-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="22796-110">Endpoint용 Defender는 고객이 플랫폼을 쉽게 채택할 수 있도록 다양한 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span>

<span data-ttu-id="22796-111">고객 환경과 구조가 다를 수 있습니다. 끝점용 Defender는 다양한 고객 요구 사항에 맞게 유연성과 세분화된 제어를 통해 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="22796-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span>

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="22796-112">끝점 온보드 및 포털 액세스</span><span class="sxs-lookup"><span data-stu-id="22796-112">Endpoint onboarding and portal access</span></span>

<span data-ttu-id="22796-113">장치 온보딩은 클라이언트 Microsoft Endpoint Manager Microsoft Intune 및 서버 장치용 Azure Defender에 완전히 통합되어 구성, 배포 및 모니터링에 대한 완전한 종단 간 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Defender for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="22796-114">또한 Endpoint용 Microsoft Defender는 그룹 정책 및 장치 관리에 사용되는 기타 타사 도구를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="22796-115">끝점용 Defender는 포털에 액세스할 수 있는 사용자가 RBAC(역할 기반 액세스 제어)의 유연성을 통해 보고 할 수 있는 작업을 세분화하여 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="22796-116">RBAC 모델은 모든 보안 팀 구조를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-116">The RBAC model supports all flavors of security teams structure:</span></span>

- <span data-ttu-id="22796-117">전역으로 분산된 조직 및 보안 팀</span><span class="sxs-lookup"><span data-stu-id="22796-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="22796-118">계층 모델 보안 운영 팀</span><span class="sxs-lookup"><span data-stu-id="22796-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="22796-119">단일 중앙 집중식 전역 보안 운영 팀을 통해 완전히 구분된 부서</span><span class="sxs-lookup"><span data-stu-id="22796-119">Fully segregated divisions with single centralized global security operations teams</span></span>

## <a name="available-apis"></a><span data-ttu-id="22796-120">사용 가능한 API</span><span class="sxs-lookup"><span data-stu-id="22796-120">Available APIs</span></span>
<span data-ttu-id="22796-121">끝점용 Microsoft Defender 솔루션은 통합 준비가 완료된 플랫폼을 토로합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="22796-122">Endpoint용 Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="22796-123">이러한 API를 통해 워크플로를 자동화하고 끝점용 Defender 기능을 기반으로 혁신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22796-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![끝점용 Microsoft Defender의 사용 가능한 API 및 통합 이미지](images/mdatp-apis.png)

<span data-ttu-id="22796-125">끝점용 Defender API는 다음 세 가지로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22796-125">The Defender for Endpoint APIs can be grouped into three:</span></span>

- <span data-ttu-id="22796-126">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22796-126">Microsoft Defender for Endpoint APIs</span></span>
- <span data-ttu-id="22796-127">원시 데이터 스트리밍 API</span><span class="sxs-lookup"><span data-stu-id="22796-127">Raw data streaming API</span></span>
- <span data-ttu-id="22796-128">SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="22796-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="22796-129">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22796-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="22796-130">Endpoint용 Defender는 사용자 또는 SaaS 응용 프로그램의 컨텍스트에서 액세스를 허용하는 표준 Azure AD 기반 인증 및 권한 부여 모델을 통해 노출되는 구조화되어 명확하며 사용하기 쉬운 모델의 데이터와 기능을 노출하는 계층화된 API 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="22796-131">API 모델은 엔터티와 기능을 일관된 형태로 표시하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="22796-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span>

<span data-ttu-id="22796-132">끝점 API용 Defender에 대한 간략한 개요는 이 비디오를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="22796-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span>
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="22796-133">조사 **API는** 계산된 또는 '프로필된' 엔터티(예: 장치, 사용자 및 파일)와 일반적으로 엔터티와 관련된 동작을 설명하는 불연결 이벤트(예: 프로세스 생성 및 파일 만들기)를 노출하여 쿼리 기반 데이터에 대한 액세스를 허용하는 조사 인터페이스를 통해 데이터에 액세스할 수 있도록 하는 엔드포인트용 Defender의 풍부한 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="22796-134">자세한 내용은 지원되는 [API를 참조하세요.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="22796-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="22796-135">응답 **API는** 서비스 및 장치에서 작업을 수행할 수 있는 기능을 노출하여 고객이 표시기를 검색하고, 설정, 경고 상태를 관리하고, 장치에서 프로그래밍식으로 장치 격리, 파일 격리 등의 응답 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span>

## <a name="raw-data-streaming-api"></a><span data-ttu-id="22796-136">원시 데이터 스트리밍 API</span><span class="sxs-lookup"><span data-stu-id="22796-136">Raw data streaming API</span></span>

<span data-ttu-id="22796-137">Endpoint 원시 데이터 스트리밍 API에 대한 Defender는 고객이 단일 데이터 스트림 내에서 발생할 때 인스턴스에서 실시간 이벤트 및 경고를 전달할 수 있도록 하여 짧은 대기 시간, 높은 처리률 전달 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22796-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="22796-138">장기 데이터 보존을 위해 Endpoint용 Defender 이벤트 정보는 Azure 저장소에 직접 푸시되거나 시각화 서비스 또는 추가 데이터 처리 엔진에서 사용할 수 있도록 Azure 이벤트 허브로 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22796-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span>

<span data-ttu-id="22796-139">자세한 내용은 원시 데이터 스트리밍 [API 를 참조하세요.](raw-data-export.md)</span><span class="sxs-lookup"><span data-stu-id="22796-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>

<span data-ttu-id="22796-140">새로운 Microsoft 365 Defender 스트리밍 API에는 장치 이벤트와 함께 전자 메일 및 경고 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="22796-140">The new Microsoft 365 Defender Streaming API includes email and alert events in addition to device events.</span></span>
<span data-ttu-id="22796-141">자세한 내용은 스트리밍 [API Microsoft 365 Defender 참조하세요.](../defender/streaming-api.md)</span><span class="sxs-lookup"><span data-stu-id="22796-141">For more information, see [Microsoft 365 Defender Streaming API](../defender/streaming-api.md).</span></span>

## <a name="siem-api"></a><span data-ttu-id="22796-142">SIEM API</span><span class="sxs-lookup"><span data-stu-id="22796-142">SIEM API</span></span>

<span data-ttu-id="22796-143">SIEM(보안 정보 및 이벤트 관리) 통합을 사용하도록 설정하면 SIEM 솔루션을 Microsoft Defender 보안 센터 검색 REST API에 직접 연결하여 검색된 검색을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22796-143">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="22796-144">이렇게 하면 미리 채워진 값이 포함된 SIEM 커넥터 액세스 세부 정보 섹션이 활성화되어 응용 프로그램이 Azure Active Directory(Azure AD) 테넌트에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="22796-144">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="22796-145">자세한 내용은 [SIEM 통합을 참조하세요.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="22796-145">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="22796-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="22796-146">Related topics</span></span>

- <span data-ttu-id="22796-147">[엔드포인트용 Microsoft Defender API에 액세스](apis-intro.md) </span><span class="sxs-lookup"><span data-stu-id="22796-147">[Access the Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>
- [<span data-ttu-id="22796-148">지원되는 API</span><span class="sxs-lookup"><span data-stu-id="22796-148">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="22796-149">기술 파트너 기회</span><span class="sxs-lookup"><span data-stu-id="22796-149">Technical partner opportunities</span></span>](partner-integration.md)