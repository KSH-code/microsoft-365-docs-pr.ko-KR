---
title: 디바이스 이름
description: 장치 Microsoft Managed Desktop 관리하는 방법
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893893"
---
# <a name="device-names"></a><span data-ttu-id="e3fae-103">디바이스 이름</span><span class="sxs-lookup"><span data-stu-id="e3fae-103">Device names</span></span>

<span data-ttu-id="e3fae-104">Microsoft Managed Desktop Autopilot, Windows, Azure Active Directory 및 Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="e3fae-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="e3fae-105">이러한 서비스가 원활하게 작동하려면 장치에 일관된 표준화된 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fae-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="e3fae-106">Microsoft Managed Desktop 등록할 때 표준화된 이름 *형식(MMD-%RAND11* 형식)이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fae-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="e3fae-107">Windows Autopilot은 이러한 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fae-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="e3fae-108">Autopilot에 대한 자세한 내용은 [Autopilot의](../get-started/esp-first-run.md)첫 실행 환경 및 등록 상태 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3fae-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="e3fae-109">자동 이름 변경</span><span class="sxs-lookup"><span data-stu-id="e3fae-109">Automated name changes</span></span>

<span data-ttu-id="e3fae-110">나중에 디바이스 이름이 변경되는 경우 Microsoft Managed Desktop 형식의 새 이름으로 자동으로 이름을 바니다.</span><span class="sxs-lookup"><span data-stu-id="e3fae-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="e3fae-111">이 프로세스는 4시간마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fae-111">This process occurs every four hours.</span></span> <span data-ttu-id="e3fae-112">다음에 사용자가 장치를 다시 시작할 때 이름 변경이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fae-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3fae-113">환경이 특정 장치 이름(예: 특정 네트워크 구성을 지원하기 위해)에 의존하는 경우 해당 종속성에 등록하기 전에 해당 종속성 제거 옵션을 조사해야 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="e3fae-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="e3fae-114">이름 종속성은 유지해야 하는 경우 관리 [](../working-with-managed-desktop/admin-support.md) 포털을 통해 요청을 제출하여 이름 변경 기능을 사용하지 않도록 설정하고 원하는 이름 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3fae-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>