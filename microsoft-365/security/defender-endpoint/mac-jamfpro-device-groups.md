---
title: Jamf Pro에서 장치 그룹 설정
description: MacOS에서 Endpoint용 Microsoft Defender용 Jamf Pro에서 장치 그룹을 설정하는 방법을 배우기
keywords: device, group, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933808"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="6a651-104">Jamf Pro에서 macOS 장치 그룹에서 끝점에 대한 Microsoft Defender 설정</span><span class="sxs-lookup"><span data-stu-id="6a651-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a651-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6a651-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a651-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6a651-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6a651-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a651-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6a651-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6a651-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a651-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6a651-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6a651-110">그룹 정책 US(조직 구성 단위), Microsoft Endpoint Configuration Manager의 장치 컬렉션 및 Intune의 장치 그룹과 유사한 장치 그룹을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a651-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="6a651-111">정적 **컴퓨터 그룹으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a651-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="6a651-112">새로 **고치기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a651-112">Select **New**.</span></span> 

    ![Jamf Pro1의 이미지](images/jamf-pro-static-group.png)

3. <span data-ttu-id="6a651-114">표시 이름을 제공하고 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a651-114">Provide a display name and select **Save**.</span></span>

    ![Jamf Pro2의 이미지](images/jamfpro-machine-group.png)

4. <span data-ttu-id="6a651-116">이제 정적 컴퓨터 그룹 아래에 **Contoso의** **컴퓨터 그룹이 표시될 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="6a651-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Jamf Pro3의 이미지](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="6a651-118">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6a651-118">Next step</span></span>
- [<span data-ttu-id="6a651-119">Jamf Pro에서 macOS 정책에 대한 끝점에 대한 Microsoft Defender 설정</span><span class="sxs-lookup"><span data-stu-id="6a651-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
