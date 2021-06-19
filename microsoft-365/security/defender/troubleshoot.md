---
title: 서비스 Microsoft 365 Defender 문제 해결
description: 알려진 문제 해결 방법 Microsoft 365 Defender 해결 방법 찾기
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
ms.openlocfilehash: 7891d61de7581a896a6599004eae91a4e47e1581
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029948"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="07150-104">서비스 Microsoft 365 Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="07150-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="07150-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="07150-105">**Applies to:**</span></span>
- <span data-ttu-id="07150-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07150-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="07150-107">이 섹션에서는 Microsoft 365 Defender 서비스를 사용할 때 발생할 수 있는 Microsoft 365 Defender 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07150-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="07150-108">콘텐츠가 Microsoft 365 Defender 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07150-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="07150-109">포털에서 인시던트, 관리 센터 또는 헌팅과 같은 탐색 창에 기능이 없는 경우 테넌트에 적절한 라이선스가 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07150-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="07150-110">자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07150-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="07150-111">Id에 대한 Microsoft Defender 경고가 문제 발생 시 Microsoft 365 Defender 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07150-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="07150-112">환경에 배포된 ID용 Microsoft Defender가 있지만 id에 대한 Defender 경고가 Microsoft 365 Defender 인시던트의 일부로 볼 수 없는 경우 id에 대한 Microsoft Cloud App Security 및 Defender 통합이 사용하도록 설정되어 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07150-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="07150-113">자세한 내용은 [Id 통합에 대한 Microsoft Defender를 참조하세요.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="07150-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="07150-114">서비스를 켜기 위한 설정 페이지는 어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="07150-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="07150-115">이 기능을 Microsoft 365 Defender 보안 **센터의** 설정 창에서 Microsoft 365 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="07150-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="07150-116">이 탐색 항목은 선행 권한 및 라이선스가 있는 [경우만 표시됩니다.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="07150-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="07150-117">내 파일/URL에 대한 예외를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="07150-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="07150-118">가짓 긍정은 악성으로 검색되지만 위협이 아닌 파일 또는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="07150-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="07150-119">표시기를 만들고 제외를 정의하여 차단을 해제하고 특정 파일/URL을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07150-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="07150-120">[끝점에 대한 Defender에서 가짓 긍정/부정 주소를 참조하세요.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)</span><span class="sxs-lookup"><span data-stu-id="07150-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>
