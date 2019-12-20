---
title: Microsoft 위협 방지 데이터 보안 및 개인 정보 보호
description: 서비스의 개인 정보 보호 및 데이터 보안에 대해 설명합니다.
keywords: 개인 정보 보호, 데이터, 보안, 보안 센터, 정보 수집
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 49574f17abee645943becc8403bef01951d31924
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806947"
---
# <a name="microsoft-threat-protection-data-security-and-privacy"></a><span data-ttu-id="24a80-104">Microsoft 위협 방지 데이터 보안 및 개인 정보 보호</span><span class="sxs-lookup"><span data-stu-id="24a80-104">Microsoft Threat Protection data security and privacy</span></span>

<span data-ttu-id="24a80-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="24a80-105">**Applies to:**</span></span>
- <span data-ttu-id="24a80-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="24a80-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="24a80-107">Microsoft 위협 방지 프리뷰를 사용하여 다음 약관에 동의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24a80-107">By using the Microsoft Threat Protection preview you consent to the following terms:</span></span>

<span data-ttu-id="24a80-108">해당 고객 데이터(온라인 서비스 약관에서 정의됨)가 다른 Microsoft 서비스에서 Microsoft 위협 방지로 전송되고 Microsoft 위협 방지에서 해당 하는 Microsoft 서비스로 다시 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="24a80-108">Your applicable Customer Data (as defined in the Online Service Terms ("OST")) will be transferred from other Microsoft services into Microsoft Threat Protection and from Microsoft Threat Protection back to applicable Microsoft services.</span></span> <span data-ttu-id="24a80-109">이 미리 보기를 진행하는 동안 Microsoft 위협 방지에서 고객 데이터를 사용하는 경우 Microsoft Defender ATP (Microsoft Defender 고급 위협 방지)에 대한 데이터 처리 표준 및 약정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="24a80-109">For the duration of this preview, use of your Customer Data in Microsoft Threat Protection will follow the data handling standards and commitments for Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP).</span></span> <span data-ttu-id="24a80-110">이러한 약정은 고객 데이터가 전송되는 서비스와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24a80-110">You acknowledge that such commitments may differ from the services from which that Customer Data is transferred.</span></span> <span data-ttu-id="24a80-111">Microsoft 위협 방지에 저장된 고객 데이터는 Microsoft Defender ATP 고객 데이터 저장소에 대해 선택한 지역에 저장되며 다른 서비스와의 연결에서 선택한 지역과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24a80-111">Further, Customer Data stored in Microsoft Threat Protection will be stored at rest in the Geo you selected for storage of your Microsoft Defender ATP Customer Data, which may differ from the Geo you selected in connection with other services.</span></span> <span data-ttu-id="24a80-112">Microsoft는 [Microsoft 보안 센터](https://www.microsoft.com/trust-center)에 위치한 Microsoft 보안 센터의 "데이터 위치" 섹션에 명시된 경우를 제외하고는 이러한 지역 외부에서 고객 데이터를 전달하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24a80-112">Microsoft will not transfer the Customer Data outside of such Geo except as noted in the "Data Location" section of the Microsoft Trust Center located at [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span>

<span data-ttu-id="24a80-113">또한 Microsoft 위협 방지에 액세스할 수 있는 사용자를 결정하는 동안 Microsoft 위협 방지는 현재 역할 기반 액세스 제어("RBAC")를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24a80-113">Further, while you determine which of your users may access Microsoft Threat Protection, Microsoft Threat Protection does not currently allow for role-based access control ("RBAC").</span></span> <span data-ttu-id="24a80-114">Microsoft 위협 방지가 RBAC를 지원하는 Microsoft 서비스에서 데이터를 수신하는 한 Microsoft 위협 방지에서는 해당 서비스의 액세스 수준이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24a80-114">You acknowledge that to the extent Microsoft Threat Protection receives data from a Microsoft service that does support RBAC, access levels in that service will not apply in Microsoft Threat Protection.</span></span>


<span data-ttu-id="24a80-115">특정 제품의 데이터 저장소 및 개인 정보 보호에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24a80-115">For more information on the data storage and privacy information of the specific products see:</span></span>
- [<span data-ttu-id="24a80-116">Microsoft Defender ATP 데이터 저장소 및 개인 정보 보호</span><span class="sxs-lookup"><span data-stu-id="24a80-116">Microsoft Defender ATP data storage and privacy</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [<span data-ttu-id="24a80-117">Microsoft Cloud App Security 데이터 보안 및 개인 정보 보호</span><span class="sxs-lookup"><span data-stu-id="24a80-117">Microsoft Cloud App Security data security and privacy</span></span>](https://docs.microsoft.com/cloud-app-security/cas-compliance-trust)
- [<span data-ttu-id="24a80-118">Office 365 개인 정보 보호, 보안 및 투명성</span><span class="sxs-lookup"><span data-stu-id="24a80-118">Office 365 privacy, security, and transparency</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/privacy-security-and-transparency#advanced-threat-protection)