---
title: 관리되는 보안 서비스 공급자 지원 구성
description: 끝점용 Microsoft Defender와 MSSP 통합을 구성하는 데 필요한 단계 수행
keywords: 관리되는 보안 서비스 공급자, mssp, 구성, 통합
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
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165252"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="8d928-104">관리되는 보안 서비스 공급자 통합 구성</span><span class="sxs-lookup"><span data-stu-id="8d928-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8d928-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8d928-105">**Applies to:**</span></span>
- [<span data-ttu-id="8d928-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8d928-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8d928-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d928-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8d928-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8d928-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8d928-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8d928-110">관리되는 보안 서비스 공급자(MSSP) 통합을 사용하도록 설정하려면 다음 구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="8d928-111">이 문서에서는 서비스 공급자와 서비스 소비자를 구분하기 위해 다음 용어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="8d928-112">MSSP: 조직의 보안 장치를 모니터링하고 관리하기 위한 보안 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="8d928-113">MSSP 고객: MSSP의 서비스를 참여하는 조직.</span><span class="sxs-lookup"><span data-stu-id="8d928-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="8d928-114">통합을 통해 MSSP는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="8d928-115">MSSP 고객의 Microsoft Defender 보안 센터 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="8d928-115">Get access to MSSP customer's Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="8d928-116">전자 메일 알림 및</span><span class="sxs-lookup"><span data-stu-id="8d928-116">Get email notifications, and</span></span> 
- <span data-ttu-id="8d928-117">SIEM(보안 정보 및 이벤트 관리) 도구를 통해 경고 페치</span><span class="sxs-lookup"><span data-stu-id="8d928-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="8d928-118">MSSP에서 이러한 작업을 수행하려면 MSSP 고객이 MSSP가 포털에 액세스할 수 있도록 끝점 테넌트에 대한 Defender에 대한 액세스 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="8d928-119">일반적으로 MSSP 고객은 초기 구성 단계를 수행하여 MSSP에 보안 중앙 테넌트에 대한 Windows Defender 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="8d928-120">액세스 권한이 부여된 후 다른 구성 단계는 MSSP 고객 또는 MSSP에서 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="8d928-121">일반적으로 다음 구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="8d928-122">**MICROSOFT Defender 보안 센터에 대한 MSSP 액세스 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="8d928-122">**Grant the MSSP access to Microsoft Defender Security Center**</span></span> <br>
<span data-ttu-id="8d928-123">이 작업은 MSSP 고객이 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="8d928-124">끝점 테넌트에 대한 MSSP 고객의 Defender 액세스 권한을 MSSP에 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="8d928-125">**MSSP로 전송된 경고 알림 구성**</span><span class="sxs-lookup"><span data-stu-id="8d928-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="8d928-126">이 작업은 MSSP 고객 또는 MSSP에서 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="8d928-127">이를 통해 MSSP는 MSSP 고객을 위해 해결해야 하는 경고를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="8d928-128">**MSSP 고객의 테넌트에서 SIEM 시스템으로 경고 페치**</span><span class="sxs-lookup"><span data-stu-id="8d928-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="8d928-129">이 작업은 MSSP에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="8d928-130">이를 통해 MSSP는 SIEM 도구에서 경고를 페치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="8d928-131">**API를 사용하여 MSSP 고객의 테넌트에서 경고 페치**</span><span class="sxs-lookup"><span data-stu-id="8d928-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="8d928-132">이 작업은 MSSP에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="8d928-133">이를 통해 MSSP는 API를 사용하여 경고를 페치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d928-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="8d928-134">MSSP에 대한 다중 테넌트 액세스</span><span class="sxs-lookup"><span data-stu-id="8d928-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="8d928-135">다중 테넌트 위임된 액세스를 구현하는 방법에 대한 자세한 내용은 관리되는 보안 서비스 공급자에 대한 다중 테넌트 [액세스를 참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)</span><span class="sxs-lookup"><span data-stu-id="8d928-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="8d928-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8d928-136">Related topics</span></span>
- [<span data-ttu-id="8d928-137">포털에 대한 MSSP 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8d928-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="8d928-138">MSSP 고객 포털 액세스</span><span class="sxs-lookup"><span data-stu-id="8d928-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="8d928-139">경고 알림 구성</span><span class="sxs-lookup"><span data-stu-id="8d928-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="8d928-140">고객 테넌트에서 경고 페치</span><span class="sxs-lookup"><span data-stu-id="8d928-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

