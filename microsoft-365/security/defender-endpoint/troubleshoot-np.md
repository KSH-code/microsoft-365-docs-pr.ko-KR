---
title: 네트워크 보호 문제 해결
description: 끝점용 Microsoft Defender의 네트워크 보호 문제를 해결하기 위한 리소스 및 샘플 코드입니다.
keywords: 문제 해결, 오류, 수정, windows defender eg, asr, 규칙, hips, 문제 해결, 감사, 제외, 가극적, 손상, 차단, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: d10399c3064697ab383133cd17cc14dc7dd43cc4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185755"
---
# <a name="troubleshoot-network-protection"></a>네트워크 보호 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

이 문서에서는 네트워크 보호 에 대한 문제 해결 정보를 [제공합니다.](network-protection.md)예:

- 네트워크 보호는 안전한 웹 사이트(가음성)를 차단합니다.
- 네트워크 보호가 의심스나 알려진 악성 웹 사이트(거짓 부정)를 차단하지 못합니다.

이러한 문제를 해결하는 네 가지 단계가 있습니다.

1. 선행 준비 확인
2. 감사 모드를 사용하여 규칙 테스트
3. 지정된 규칙에 대한 제외 추가(가음성의 경우)
4. 지원 로그 제출

## <a name="confirm-prerequisites"></a>선행 준비 확인

네트워크 보호는 다음 조건이 있는 디바이스에서만 작동합니다.

> [!div class="checklist"]
>
> - 끝점에서 Windows 10 Pro 버전 Enterprise 버전 1709 이상을 실행하고 있습니다.
> - 끝점에서 단독 Microsoft Defender 바이러스 백신 보호 앱으로 사용하고 있습니다. [Microsoft가 아닌 바이러스 백신](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)솔루션을 사용할 때 발생하는 문제를 참조합니다.
> - [실시간 보호가](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 사용됩니다.
> - [클라우드 제공 보호를](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 사용할 수 있습니다.
> - 감사 모드를 사용할 수 없습니다. 그룹 [정책을 사용하여](enable-network-protection.md#group-policy) 규칙을 사용 안 하게 **설정(값:** **0)합니다.**

## <a name="use-audit-mode"></a>감사 모드 사용

감사 모드에서 네트워크 보호를 사용하도록 설정한 다음 기능을 데모하기 위해 만든 웹 사이트를 방문할 수 있습니다. 모든 웹 사이트 연결은 네트워크 보호에서 허용되지만 네트워크 보호를 사용하도록 설정한 경우 차단될 모든 연결을 나타내는 이벤트가 기록됩니다.

1. 네트워크 보호를 감사 **모드로 설정**

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. 문제를 일으키는 연결 활동을 수행합니다(예: 사이트를 방문하거나 차단하려는 IP 주소에 연결하려고 시도).

3. [네트워크 보호 이벤트](network-protection.md#review-network-protection-events-in-windows-event-viewer) 로그를 검토하여 기능이 사용으로 설정된 경우 연결을 차단할 수 없는지 **확인합니다.**

   네트워크 보호가 차단해야 하는 연결을 차단하지 않는 경우 기능을 사용하도록 설정하십시오.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>가짓 긍정 또는 거짓 부정 보고

데모 사이트 및 감사 모드로 기능을 테스트했지만 네트워크 보호가 미리 구성된 시나리오에서 작동하지만 특정 연결에 대해 예상대로 작동하지 않는 경우 [Windows Defender 보안](https://www.microsoft.com/wdsi/filesubmission) 인텔리전스 웹 기반 제출 양식을 사용하여 네트워크 보호에 대한 거짓 부정 또는 가양성 보고를 합니다. E5 구독을 사용하면 연결된 경고에 대한 링크를 [제공할 수도 있습니다.](alerts-queue.md)

끝점에 대한 [Microsoft Defender의 가짓 긍정/부정 주소를 참조하세요.](defender-endpoint-false-positives-negatives.md)

## <a name="add-exclusions"></a>제외 추가
현재 제외 옵션은 다음과 같습니다.

1.  사용자 지정 허용 표시기 설정
2.  IP 제외 사용: `Add-MpPreference -Exclusion IpAddress 192.168.1.1`
3.  전체 프로세스를 제외합니다. 자세한 내용은 제외 [Microsoft Defender 바이러스 백신 참조하세요.](configure-exclusions-microsoft-defender-antivirus.md) 


## <a name="collect-diagnostic-data-for-file-submissions"></a>파일 전송에 대한 진단 데이터 수집

네트워크 보호 관련 문제를 보고하는 경우 Microsoft 지원 및 엔지니어링 팀에서 문제를 해결하는 데 사용할 수 있는 진단 데이터를 수집하고 제출해야 합니다.

1. 승강된 명령 프롬프트를 열고 Windows Defender 변경합니다.

   ```console
   cd c:\program files\windows defender
   ```

2. 다음 명령을 실행하여 진단 로그를 생성합니다.

   ```console
   mpcmdrun -getfiles
   ```

3. 파일을 제출 양식에 첨부합니다. 기본적으로 진단 로그는 에 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 저장됩니다.

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>네트워크 보호 관련 연결 문제 해결(E5 고객용)

네트워크 보호가 실행되는 환경으로 인해 Microsoft는 운영 체제 프록시 설정을 볼 수 없습니다. 경우에 따라 네트워크 보호 클라이언트가 클라우드 서비스에 연결하지 못할 수 있습니다. 네트워크 보호와의 연결 문제를 해결하려면 네트워크 보호에서 프록시 구성을 인식하도록 다음 레지스트리 키 중 하나를 구성합니다.

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---OR---

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

PowerShell, 그룹 정책 또는 그룹 정책을 사용하여 Microsoft Endpoint Manager 수 있습니다. 다음은 도움이 되는 몇 가지 리소스입니다.

- [레지스트리 키 작업](/powershell/scripting/samples/working-with-registry-keys)
- [사용자 지정 클라이언트 설정 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [그룹 정책 설정을 사용하여 그룹 정책 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>참고 항목

- [네트워크 보호](network-protection.md)
- [네트워크 보호 및 TCP 3차원 핸드세이크](network-protection.md#network-protection-and-the-tcp-three-way-handshake)
- [네트워크 보호 평가](evaluate-network-protection.md)
- [네트워크 보호 사용](enable-network-protection.md)
- [끝점용 Defender에서 가짓 긍정/음수 해결](defender-endpoint-false-positives-negatives.md)
