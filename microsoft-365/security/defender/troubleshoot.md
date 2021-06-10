---
title: Defender Microsoft 365 문제 해결
description: 알려진 Defender 문제에 대한 해결 Microsoft 365 해결 방법 찾기
keywords: 문제 Microsoft 365 Defender, 문제 해결, ID에 대한 Microsoft Defender, 문제, 추가 기능, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782744"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="a7dd6-104">Defender Microsoft 365 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a7dd6-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a7dd6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a7dd6-105">**Applies to:**</span></span>
- <span data-ttu-id="a7dd6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7dd6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a7dd6-107">이 섹션에서는 Defender 서비스를 사용할 때 Microsoft 365 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="a7dd6-108">Defender 콘텐츠가 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="a7dd6-109">포털에서 인시던트, 관리 센터 또는 헌팅과 같은 탐색 창에 기능이 없는 경우 테넌트에 적절한 라이선스가 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="a7dd6-110">자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="a7dd6-111">Id에 대한 Microsoft Defender 경고가 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="a7dd6-112">환경에 배포된 ID용 Microsoft Defender가 있지만 Microsoft 365 Defender 인시던트의 일부로 ID 경고에 대한 Defender가 없는 경우 id에 대한 Microsoft Cloud App Security 및 Defender 통합이 사용하도록 설정되어 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="a7dd6-113">자세한 내용은 [Id 통합에 대한 Microsoft Defender를 참조하세요.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="a7dd6-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="a7dd6-114">서비스를 켜기 위한 설정 페이지는 어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="a7dd6-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="a7dd6-115">Defender를 Microsoft 365 설정하기 위해  설정 센터의 탐색 창에서 Microsoft 365 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="a7dd6-116">이 탐색 항목은 선행 권한 및 라이선스가 있는 [경우만 표시됩니다.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="a7dd6-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="a7dd6-117">내 파일/URL에 대한 예외를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="a7dd6-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="a7dd6-118">가짓 긍정은 악성으로 검색되지만 위협이 아닌 파일 또는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="a7dd6-119">표시기를 만들고 제외를 정의하여 차단을 해제하고 특정 파일/URL을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7dd6-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="a7dd6-120">[끝점에 대한 Defender에서 가짓 긍정/부정 주소를 참조하세요.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)</span><span class="sxs-lookup"><span data-stu-id="a7dd6-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


