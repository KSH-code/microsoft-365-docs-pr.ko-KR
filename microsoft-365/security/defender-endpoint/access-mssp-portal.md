---
title: MSSP Microsoft Defender 보안 센터 포털에 액세스
description: MSSP Microsoft Defender 보안 센터 포털에 액세스
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164860"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="16c35-104">MSSP Microsoft Defender 보안 센터 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="16c35-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="16c35-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="16c35-105">**Applies to:**</span></span>
- [<span data-ttu-id="16c35-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="16c35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16c35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16c35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="16c35-108">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="16c35-108">**Applies to:**</span></span>

- [<span data-ttu-id="16c35-109">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="16c35-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="16c35-110">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="16c35-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="16c35-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="16c35-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="16c35-112">이러한 단계 집합은 MSSP로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="16c35-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="16c35-113">기본적으로 MSSP 고객은 다음 URL을 Microsoft Defender 보안 센터 테넌트에 `https://securitycenter.windows.com` 액세스합니다. .</span><span class="sxs-lookup"><span data-stu-id="16c35-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="16c35-114">그러나 MSSP는 MSSP 고객 포털에 액세스하려면 다음과 같은 형식으로  `https://securitycenter.windows.com?tid=customer_tenant_id` 테넌트별 URL을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c35-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="16c35-115">일반적으로 MSSP는 관리하려는 각 MSSP 고객의 Azure AD에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c35-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="16c35-116">다음 단계에 따라 MSSP 고객 테넌트 ID를 얻은 다음 ID를 사용하여 테넌트 관련 URL에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="16c35-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="16c35-117">MSSP로 자격 증명을 사용하여 Azure AD에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="16c35-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="16c35-118">디렉터리를 MSSP 고객의 테넌트로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="16c35-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="16c35-119">속성 **Azure Active Directory > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="16c35-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="16c35-120">디렉터리 ID 필드에서 테넌트 ID를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16c35-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="16c35-121">다음 URL의 값을 바 사용하여 MSSP 고객 `customer_tenant_id` 포털에 `https://securitycenter.windows.com?tid=customer_tenant_id` 액세스합니다. .</span><span class="sxs-lookup"><span data-stu-id="16c35-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="16c35-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="16c35-122">Related topics</span></span>
- [<span data-ttu-id="16c35-123">MSSP 액세스를 포털에 부여</span><span class="sxs-lookup"><span data-stu-id="16c35-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="16c35-124">경고 알림 구성</span><span class="sxs-lookup"><span data-stu-id="16c35-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="16c35-125">고객 테넌트에서 경고 페치</span><span class="sxs-lookup"><span data-stu-id="16c35-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
