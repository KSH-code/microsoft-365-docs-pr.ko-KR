---
title: 주소 장치 이름 종속성
description: 장치 이름에 대한 종속성 제거 또는 예외 요청
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
ms.openlocfilehash: 8c82acb5306e3add7c41fd4e6f7e313782d47574
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893903"
---
# <a name="address-device-name-dependency"></a><span data-ttu-id="8b5cd-103">주소 장치 이름 종속성</span><span class="sxs-lookup"><span data-stu-id="8b5cd-103">Address device name dependency</span></span>

<span data-ttu-id="8b5cd-104">Microsoft Managed Desktop은 장치가 등록될 때 표준화된 이름 형식을 적용하며 나중에 이름이 변경되는 경우 자동으로 디바이스 이름을 바꿔 집니다.</span><span class="sxs-lookup"><span data-stu-id="8b5cd-104">Microsoft Managed Desktop applies a standardized name format when devices are enrolled and will automatically rename devices if the name is changed later.</span></span> <span data-ttu-id="8b5cd-105">자세한 내용은 장치 이름을 [참조하세요.](../service-description/device-names.md)</span><span class="sxs-lookup"><span data-stu-id="8b5cd-105">For more info, see [Device names](../service-description/device-names.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b5cd-106">환경이 특정 장치 이름(예: 특정 네트워크 구성 지원)에 종속되는 경우 Microsoft Managed Desktop에 등록하기 전에 해당 종속성 제거 옵션을 조사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5cd-106">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="8b5cd-107">이름 종속성은 유지해야 하는 경우 관리 [](../working-with-managed-desktop/admin-support.md) 포털을 통해 요청을 제출하여 이름 변경 기능을 사용하지 않도록 설정하고 원하는 이름 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5cd-107">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>