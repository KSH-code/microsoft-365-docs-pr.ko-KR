---
title: 자동화된 조사 및 수정 기능 구성
description: 끝점용 Microsoft Defender에서 자동화된 조사 및 수정 기능을 설정합니다.
keywords: 구성, 설정, 자동화, 조사, 검색, 경고, 수정, 응답
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 87e27933d051a0e1ed8b69c9e7e7dbe37a9d11e5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211279"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 자동화된 조사 및 수정 기능 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

조직에서 [끝점용 Microsoft Defender(Endpoint용 Defender)를](/windows/security/threat-protection/) 사용하는 경우 [자동화된](/microsoft-365/security/defender-endpoint/automated-investigations) 조사 및 수정 기능을 통해 보안 운영 팀의 시간과 노력을 절약할 수 있습니다. 이 블로그 [](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)게시물에 설명된 것 처럼 이러한 기능은 보안 분석가가 위협을 조사하고 수정하는 데 걸리는 이상적인 단계와 모방합니다. [자동화된 조사 및 수정에 대해 자세히 알아보시겠어요.](/microsoft-365/security/defender-endpoint/automated-investigations)

자동화된 조사 및 수정을 구성합니다.

1. [기능 켜기](#turn-on-automated-investigation-and-remediation); 및
2. [장치 그룹 설정](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>자동화된 조사 및 수정 켜기

1. 전역 관리자 또는 보안 관리자는 <https://securitycenter.windows.com> Microsoft Defender 보안 센터()로 이동하여 로그인합니다.
2. 탐색 창에서 를 **설정.**
3. 일반 **섹션에서** 고급 기능을 **선택합니다.**
4. 자동 조사 **및** **경고 자동 해결을 둘 다 니다.**

## <a name="set-up-device-groups"></a>장치 그룹 설정

1. in the Microsoft Defender 보안 센터 ( <https://securitycenter.windows.com> ) on the **설정** page, under **Permissions**, select **Device groups**.
2. **+ 장치 그룹 추가를 선택합니다.**
3. 다음과 같이 하나 이상의 장치 그룹을 만들 수 있습니다.
   - 디바이스 그룹의 이름과 설명을 지정합니다.
   - 자동화 **수준 목록에서** 수준(예: 전체 - 위협 자동 **수정)을 선택합니다.** 자동화 수준은 수정 작업이 자동으로 수행될지 승인 시에만 수행될지 여부를 결정합니다. 자세한 내용은 자동화된 조사 및 수정의 자동화 수준을 [참조합니다.](automation-levels.md)
   - 구성원 **섹션에서** 하나 이상의 조건을 사용하여 장치를 식별하고 포함합니다.
   - 사용자 **액세스 탭에서** 만들 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) 액세스할 수 있는 사용자 그룹 그룹을 선택합니다.
4. 디바이스 **그룹** 설정이 완료되면 완료를 선택합니다.

## <a name="next-steps"></a>다음 단계

- [관리 센터를 방문하여 보류 중 및 완료된 수정 작업 보기](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [보류 중인 작업 검토 및 승인](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>참고 항목

- [Endpoint용 Microsoft Defender에서 가양성/가음성 처리](defender-endpoint-false-positives-negatives.md)
