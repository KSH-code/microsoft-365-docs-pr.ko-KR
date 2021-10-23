---
title: 클라우드 Microsoft Defender 바이러스 백신 제한 시간 구성
description: 클라우드 결정이 Microsoft Defender 바이러스 백신 동안 파일이 실행되지 못하도록 차단하는 기간을 구성할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 클라우드, 시간 제한, 차단, 기간, 초
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: b00c631a3eeaddb4fa66fe6d58fd40418b188bec
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552731"
---
# <a name="configure-the-cloud-block-timeout-period"></a>클라우드 차단 제한 시간 구성

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

사용자가 Microsoft Defender 바이러스 백신 파일을 찾은 경우 클라우드 서비스 에 쿼리하는 동안 파일이 [실행되지 Microsoft Defender 바이러스 백신 있습니다.](cloud-protection-microsoft-defender-antivirus.md)

파일이 차단된 기본 [기간은](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10초입니다. 보안 관리자인 경우 파일을 실행할 수 있도록 허용되기 전에 대기할 시간을 더 지정할 수 있습니다. 클라우드 차단 시간 제한 기간을 연장하면 클라우드 서비스에서 적절한 확인을 받을 Microsoft Defender 바이러스 백신 있습니다.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>확장된 클라우드 차단 시간 제한을 사용하기 위한 선행 준비

[제한 시간을](configure-block-at-first-sight-microsoft-defender-antivirus.md) 연장하려면 먼저 차단 및 해당 선행 조건이 활성화되어야 합니다.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>제한 시간을 사용하여 연장된 시간 제한 Microsoft Endpoint Manager

에서 끝점 보안 정책을 사용하여 클라우드 차단 시간 제한 기간을 [지정할 Microsoft Endpoint Manager.](/mem/intune/protect/endpoint-security-policy)

1. Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) 로그인합니다.

2. 끝점 **보안 을 선택한** 다음 관리 **에서** 바이러스 백신 을 **선택합니다.**

3. 바이러스 백신 정책을 선택(또는 만들기)합니다.

4. 구성 **설정 섹션에서** 클라우드 **보호를 확장합니다.** 그런 다음 **Defender 클라우드** 확장 시간 제한(초) 상자에 1초에서 50초까지 더 많은 시간을 초당 지정합니다. 지정한 모든 것이 기본 10초에 추가됩니다.

5. (이 단계는 선택 사항임) 바이러스 백신 정책을 다른 변경합니다. (도움이 필요하세요? 자세한 [설정 에서 Microsoft Defender 바이러스 백신 정책에 대한 Microsoft Intune.)를 참조합니다.](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)

6. 다음 **을** 선택하고 정책 구성을 완료합니다.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>그룹 정책을 사용하여 연장된 시간 제한 기간 지정

그룹 정책을 사용하여 클라우드 검사에 대한 연장된 시간 제한을 지정할 수 있습니다.

1. 그룹 정책 관리 컴퓨터에서 그룹 정책 관리 [콘솔을 열기](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 을 **선택합니다.**

3. 그룹 **정책 관리 편집기에서** 컴퓨터 구성으로 **이동한** 다음 관리 템플릿 **을 선택합니다.**

3. 트리를 확장하여  \>  \> **MpEngine** Windows 구성 Microsoft Defender 바이러스 백신 확장합니다.

4. 확장된 클라우드 확인 구성을 두 **번 클릭하고** 옵션이 사용하도록 설정되어 있는지 확인합니다. 

   클라우드 확인을 기다리는 동안 파일이 실행되지 않도록 추가 시간을 지정합니다. 추가 시간을 초당 1초에서 50초로 지정합니다. 지정한 모든 것이 기본 10초에 추가됩니다.

5. **확인** 을 선택합니다.

 