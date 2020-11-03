---
title: Microsoft 365 Defender 서비스 문제 해결
description: 알려진 Microsoft 365 Defender 문제에 대 한 해결 방법 및 해결 방법 찾기
keywords: Microsoft Threat Protection, 문제 해결, Azure ATP, 문제, 추가 기능, 설정 페이지 문제 해결
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844671"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="d4a8e-104">Microsoft 365 Defender 서비스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d4a8e-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4a8e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d4a8e-105">**Applies to:**</span></span>
- <span data-ttu-id="d4a8e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4a8e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d4a8e-107">이 섹션에서는 Microsoft 365 Defender 서비스를 사용할 때 발생할 수 있는 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>


## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="d4a8e-108">Microsoft 365 Defender 콘텐츠가 표시 되지 않음</span><span class="sxs-lookup"><span data-stu-id="d4a8e-108">I don't see Microsoft 365 Defender content</span></span>
<span data-ttu-id="d4a8e-109">포털의 인시던트, 작업 센터 또는 검색 등의 기능이 탐색 창에 표시 되지 않는 경우에는 테 넌 트에 적절 한 라이선스가 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="d4a8e-110">자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="d4a8e-111">Microsoft Defender for Identity alerts for Id 365 알림</span><span class="sxs-lookup"><span data-stu-id="d4a8e-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>
<span data-ttu-id="d4a8e-112">사용자 환경에 Microsoft Defender for Identity가 배포 되어 있지만 Microsoft 365 Defender 인시던트의의 일환으로 Id 알림을 위한 Defender가 표시 되지 않는 경우 Microsoft Cloud App Security 및 Defender for Identity 통합을 사용 하도록 설정 했는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span> 

<span data-ttu-id="d4a8e-113">자세한 내용은 [id 통합용 Microsoft Defender](https://docs.microsoft.com/cloud-app-security/aatp-integration)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="d4a8e-114">서비스를 켜는 설정 페이지는 어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="d4a8e-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="d4a8e-115">Microsoft 365 Defender를 켜려면 Microsoft 365 보안 센터의 탐색 창에서 **설정** 에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="d4a8e-116">이 탐색 항목은 [필수 사용 권한 및 라이선스가](mtp-enable.md#check-license-eligibility-and-required-permissions)있는 경우에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

