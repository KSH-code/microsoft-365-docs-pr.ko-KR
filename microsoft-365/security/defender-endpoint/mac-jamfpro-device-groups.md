---
title: Jamf 2013에서 장치 Pro
description: MacOS에서 Microsoft Defender for Endpoint용 Pro Jamf 에서 장치 그룹을 설정하는 방법에 대해 자세히 알아보기
keywords: device, group, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 29f67b4bd96775494064789a57ae7e53e6d0d77a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207802"
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
