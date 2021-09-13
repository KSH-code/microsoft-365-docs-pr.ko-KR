---
title: Jamf 2013에서 장치 Pro
description: MacOS에서 Microsoft Defender for Endpoint용 Pro Jamf 에서 장치 그룹을 설정하는 방법에 대해 자세히 알아보기
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
ms.openlocfilehash: 6a9c3a567bed4ac337e804e53807570c53304027
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212105"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Jamf 2013에서 macOS 장치 그룹에서 끝점에 대한 Microsoft Defender Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

그룹 정책 US(조직 구성 단위), Microsoft Endpoint Configuration Manager 및 Intune의 장치 그룹과 유사한 장치 그룹을 설정합니다.

1. 정적 **컴퓨터 그룹으로 이동합니다.**

2. 새로 **고치기 를 선택합니다.** 

    ![Jamf Pro1의 이미지입니다.](images/jamf-pro-static-group.png)

3. 표시 이름을 제공하고 저장을 **선택합니다.**

    ![Jamf Pro2의 이미지입니다.](images/jamfpro-machine-group.png)

4. 이제 정적 컴퓨터 그룹 아래에 **Contoso의** **컴퓨터 그룹이 표시될 것입니다.**

    ![Jamf Pro3의 이미지입니다.](images/contoso-machine-group.png)

## <a name="next-step"></a>다음 단계
- [Jamf 2013에서 macOS 정책에 대한 끝점에 대한 Microsoft Defender Pro](mac-jamfpro-policies.md)
