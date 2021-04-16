---
title: Jamf Pro에서 장치 그룹 설정
description: MacOS용 끝점용 Microsoft Defender용 Jamf Pro에서 장치 그룹을 설정하는 방법에 대해 자세히 알아보기
keywords: device, group, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 80dcb4ff73edd5e95603b15e097232a43dc0e05e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861614"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Jamf Pro에서 macOS 장치 그룹에서 끝점에 대한 Microsoft Defender 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

그룹 정책 US(조직 구성 단위), Microsoft Endpoint Configuration Manager의 장치 컬렉션 및 Intune의 장치 그룹과 유사한 장치 그룹을 설정합니다.

1. 정적 **컴퓨터 그룹으로 이동합니다.**

2. 새로 **고치기 를 선택합니다.** 

    ![Jamf Pro1의 이미지](images/jamf-pro-static-group.png)

3. 표시 이름을 제공하고 저장을 **선택합니다.**

    ![Jamf Pro2의 이미지](images/jamfpro-machine-group.png)

4. 이제 정적 컴퓨터 그룹 아래에 **Contoso의** **컴퓨터 그룹이 표시될 것입니다.**

    ![Jamf Pro3의 이미지](images/contoso-machine-group.png)

## <a name="next-step"></a>다음 단계
- [Jamf Pro에서 macOS 정책에 대한 끝점에 대한 Microsoft Defender 설정](mac-jamfpro-policies.md)
