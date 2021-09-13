---
title: Mac의 끝점용 Microsoft Defender 설치 문제 해결
description: Mac의 끝점용 Microsoft Defender에서 설치 문제를 해결합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치
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
ms.openlocfilehash: 776cd18146fa4f726ef5d25433c564510b8a0e67
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215005"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS의 끝점용 Microsoft Defender 설치 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [Microsoft Defender for Endpoint(macOS용)](microsoft-defender-endpoint-mac.md)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>설치 실패

수동 설치의 경우 설치 마법사의 요약 페이지에 "설치하는 동안 오류가 발생했습니다. 설치 관리자에서 오류가 발생하여 설치가 실패했습니다. 소프트웨어 제조업체에 문의하여 도움을 요청하세요." MDM 배포의 경우 일반 설치 실패로도 표시됩니다.

최종 사용자에게 정확한 오류가 표시되지는는 하지만 설치 진행률이 있는 로그 파일은 에 `/Library/Logs/Microsoft/mdatp/install.log` 보관합니다. 각 설치 세션은 이 로그 파일에 추가됩니다. 마지막 설치 `sed` 세션만 출력하는 데 사용할 수 있습니다.

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

이 예제에서는 실제 이유에 를(를) `[ERROR]` 제공합니다.
이러한 버전 간 다운그레이드가 지원되지 않는 경우 설치에 실패했습니다.

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP 설치 로그가 누락되거나 업데이트되지 않습니다.

드물지만 설치는 MDATP의 /Library/Logs/Microsoft/mdatp/install.log 파일에 추적을 남기지 않습니다.
macOS 로그를 쿼리하여 설치가 발생했다는 사실과 가능한 오류를 분석할 수 있습니다(클라이언트 UI가 없는 경우 MDM 배포에 유용합니다). 많은 정보가 제공될 수 있도록 좁은 시간 창을 사용하여 쿼리를 실행하고 로깅 프로세스 이름을 사용하여 필터링하는 것이 좋습니다.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
