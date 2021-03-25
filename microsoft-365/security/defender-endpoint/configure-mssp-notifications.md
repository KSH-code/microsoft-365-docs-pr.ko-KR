---
title: MSSP로 전송된 경고 알림 구성
description: MSSP로 전송된 경고 알림 구성
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166056"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="6153e-104">MSSP로 전송된 경고 알림 구성</span><span class="sxs-lookup"><span data-stu-id="6153e-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6153e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6153e-105">**Applies to:**</span></span>
- [<span data-ttu-id="6153e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6153e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6153e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6153e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6153e-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6153e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6153e-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6153e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="6153e-110">이 단계는 MSSP 고객 또는 MSSP에서 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6153e-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="6153e-111">MSSP 고객을 대신하여 이를 구성하려면 MSSP에 적절한 사용 권한이 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6153e-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="6153e-112">포털에 액세스 권한이 부여되면 테넌트와 연결된 경고가 생성되어 조건을 설정할 때 전자 메일이 MSSP로 전송될 수 있도록 경고 알림 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6153e-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="6153e-113">자세한 내용은 [경고 알림에 대한 규칙 만들기를 참조하세요.](configure-email-notifications.md#create-rules-for-alert-notifications)</span><span class="sxs-lookup"><span data-stu-id="6153e-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="6153e-114">이러한 확인란은 다음을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6153e-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="6153e-115">**조직 이름 포함** - 고객 이름이 전자 메일 알림에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6153e-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="6153e-116">**테넌트별** 포털 링크 포함 - 경고 링크 URL에는 대상 테넌트 포털에 직접 액세스할 수 있는 테넌트별 매개 변수(tid=target_tenant_id)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6153e-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="6153e-117">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6153e-117">Related topics</span></span>
- [<span data-ttu-id="6153e-118">포털에 대한 MSSP 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="6153e-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="6153e-119">MSSP 고객 포털 액세스</span><span class="sxs-lookup"><span data-stu-id="6153e-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="6153e-120">고객 테넌트에서 경고 페치</span><span class="sxs-lookup"><span data-stu-id="6153e-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
