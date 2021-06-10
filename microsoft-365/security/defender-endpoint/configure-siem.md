---
title: 끝점용 Microsoft Defender에서 SIEM 도구로 검색 끌어오기
description: REST API를 사용하는 방법을 알아보고 검색을 수신하고 끌어오도록 지원되는 보안 정보 및 이벤트 관리 도구를 구성합니다.
keywords: siem 구성, 보안 정보 및 이벤트 관리 도구, splunk, arcsight, 사용자 지정 표시기, rest api, 경고 정의, 손상 표시기
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222338"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="87a6c-104">SIEM 도구로 검색 끌어오기</span><span class="sxs-lookup"><span data-stu-id="87a6c-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="87a6c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="87a6c-105">**Applies to:**</span></span>
- [<span data-ttu-id="87a6c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="87a6c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="87a6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87a6c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="87a6c-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="87a6c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="87a6c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="87a6c-110">SIEM(보안 정보 및 이벤트 관리) 도구를 사용하여 검색 끌어오기</span><span class="sxs-lookup"><span data-stu-id="87a6c-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="87a6c-111">[끝점용 Microsoft Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="87a6c-112">[끝점 검색을 위한 Microsoft Defender는](api-portal-mapping.md) 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="87a6c-113">-The Microsoft Defender for Endpoint Alert API는 경고 소비를 위한 최신 API로, 각 경고에 대한 자세한 관련 증거 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="87a6c-114">자세한 내용은 [Alert 메서드](alerts.md) 및 속성 및 목록 [경고를 참조하세요.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="87a6c-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="87a6c-115">Endpoint용 Defender는 검색을 끌어오기 위한 SIEM(보안 정보 및 이벤트 관리) 도구를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="87a6c-116">Endpoint용 Defender는 Azure에서 호스트된 HTTPS 끝점을 통해 경고를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="87a6c-117">환경에 설치된 특정 SIEM 커넥터를 나타내는 AAD 응용 프로그램에 대해 OAuth 2.0 인증 프로토콜을 사용하여 AAD(Azure Active Directory)의 엔터프라이즈 테넌트에서 검색을 끌어오도록 끝점을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="87a6c-118">Endpoint용 Defender는 현재 전용 SIEM 통합 모델을 통해 다음과 같은 특정 SIEM 솔루션 도구를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="87a6c-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="87a6c-119">IBM QRadar</span></span>
- <span data-ttu-id="87a6c-120">마이크로 포커스 ArcSight</span><span class="sxs-lookup"><span data-stu-id="87a6c-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="87a6c-121">Splunk, RSA NetWitness 등의 다른 SIEM 솔루션은 새로운 경고 API를 기반으로 하는 다른 통합 모델을 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="87a6c-122">자세한 내용은 파트너 [](https://securitycenter.microsoft.com/interoperability/partners) 응용 프로그램 페이지를 보고 전체 세부 정보를 확인하려면 보안 정보 및 분석 섹션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="87a6c-123">지원되는 SIEM 도구 중 하나를 사용하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="87a6c-124">Endpoint용 Defender에서 SIEM 통합 사용</span><span class="sxs-lookup"><span data-stu-id="87a6c-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="87a6c-125">지원되는 SIEM 도구를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6c-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="87a6c-126">엔드포인트 감지를 위해 Defender를 끌어오도록 마이크로 포커스 ArcSight 구성</span><span class="sxs-lookup"><span data-stu-id="87a6c-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="87a6c-127">끝점 검색을 위해 Defender를 끌어오도록 IBM QRadar 구성 자세한 내용은 [IBM 기술 센터를 참조하세요.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="87a6c-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="87a6c-128">검색 API에 노출된 필드 목록에 대한 자세한 내용은 Endpoint 검색 [필드에 대한 Defender를 참조하세요.](api-portal-mapping.md)</span><span class="sxs-lookup"><span data-stu-id="87a6c-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
