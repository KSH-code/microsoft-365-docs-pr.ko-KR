---
title: 끝점용 Microsoft Defender의 연결된 응용 프로그램
ms.reviewer: ''
description: 표준 OAuth 2.0 프로토콜을 사용하여 Microsoft Defender for Endpoint API와 함께 사용할 토큰을 인증하고 제공하는 연결된 파트너 응용 프로그램을 볼 수 있습니다.
keywords: 파트너, 응용 프로그램, 타사, 연결, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, 더 나은 모바일
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
ms.technology: mde
ms.openlocfilehash: 06ef716e9deee7b20e8615bd22c93130ee18b77f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845585"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="eaf9d-104">끝점용 Microsoft Defender의 연결된 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="eaf9d-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eaf9d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="eaf9d-105">**Applies to:**</span></span>
- [<span data-ttu-id="eaf9d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eaf9d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eaf9d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eaf9d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="eaf9d-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="eaf9d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eaf9d-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="eaf9d-110">연결된 응용 프로그램은 API를 사용하여 끝점용 Defender 플랫폼과 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="eaf9d-111">응용 프로그램은 표준 OAuth 2.0 프로토콜을 사용하여 끝점 API용 Microsoft Defender에서 사용할 토큰을 인증하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="eaf9d-112">또한 Azure AD(Azure Active Directory) 응용 프로그램을 통해 테넌트 관리자는 해당 앱을 사용하여 액세스할 수 있는 API에 대한 명시적 컨트롤을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="eaf9d-113">연결된 응용 프로그램에서 [](/microsoft-365/security/defender-endpoint/apis-intro) API를 사용하려면 다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-113">You'll need to follow [these steps](/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="eaf9d-114">연결된 응용 프로그램 페이지에 액세스</span><span class="sxs-lookup"><span data-stu-id="eaf9d-114">Access the connected application page</span></span>
<span data-ttu-id="eaf9d-115">왼쪽 탐색 메뉴에서 **파트너**& API 연결된 AAD 응용  >  **프로그램을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eaf9d-115">From the left navigation menu, select **Partners & APIs** > **Connected AAD applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="eaf9d-116">연결된 응용 프로그램 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="eaf9d-116">View connected application details</span></span>
<span data-ttu-id="eaf9d-117">연결된 응용 프로그램 페이지에서는 조직의 끝점용 Microsoft Defender에 연결된 Azure AD 응용 프로그램에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="eaf9d-118">마지막으로 확인한 응용 프로그램, 지난 24시간 동안의 요청 수 및 지난 30일 동안의 추세 요청과 같은 연결된 응용 프로그램의 사용을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![연결된 앱의 이미지](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="eaf9d-120">연결된 응용 프로그램 편집, 다시 구성 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="eaf9d-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="eaf9d-121">응용 **프로그램 설정 열기 링크를** 클릭하면 Azure Portal에서 해당 Azure AD 응용 프로그램 관리 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="eaf9d-122">Azure Portal에서 연결된 응용 프로그램을 관리하거나, 다시 구성하거나, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf9d-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
