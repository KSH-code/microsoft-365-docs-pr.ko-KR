---
title: Microsoft 365 Defender 서비스 문제 해결
description: 해결 방법 찾기 및 알려진 Microsoft 365 Defender 문제 해결
keywords: Microsoft 위협 방지 문제 해결, 문제 해결, Azure ATP, 문제, 추가 기능, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d01912532ad2a00abbecee0d0a337be7baf87017
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918669"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="000c6-104">Microsoft 365 Defender 서비스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="000c6-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="000c6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="000c6-105">**Applies to:**</span></span>
- <span data-ttu-id="000c6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="000c6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="000c6-107">이 섹션에서는 Microsoft 365 Defender 서비스를 사용할 때 발생할 수 있는 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="000c6-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="000c6-108">Microsoft 365 Defender 콘텐츠가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="000c6-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="000c6-109">포털에서 인시던트, 관리 센터 또는 헌팅과 같은 탐색 창에 기능이 없는 경우 테넌트에 적절한 라이선스가 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="000c6-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="000c6-110">자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="000c6-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="000c6-111">Id에 대한 Microsoft Defender 알림이 Microsoft 365 Defender 인시던트에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="000c6-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="000c6-112">환경에 배포된 ID용 Microsoft Defender가 있지만 Microsoft 365 Defender 인시던트의 일부로 ID에 대한 Defender 경고가 없는 경우 Microsoft Cloud App Security 및 Id용 Defender 통합이 사용하도록 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="000c6-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="000c6-113">자세한 내용은 [Id 통합에 대한 Microsoft Defender를 참조하세요.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="000c6-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="000c6-114">서비스를 켜기 위한 설정 페이지는 어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="000c6-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="000c6-115">Microsoft 365 Defender를 켜기 위해 Microsoft 365 보안 센터의 탐색 창에서 설정에 액세스합니다. </span><span class="sxs-lookup"><span data-stu-id="000c6-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="000c6-116">이 탐색 항목은 선행 권한 및 라이선스가 있는 [경우만 표시됩니다.](mtp-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="000c6-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>