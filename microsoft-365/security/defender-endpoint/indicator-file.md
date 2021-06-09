---
title: 파일에 대한 지표 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 파일 해시에 대한 표시기를 만들 수 있습니다.
keywords: 파일, 해시, 관리, 허용, 차단, 차단, 정리, 악성, 파일 해시, ip 주소, URL, 도메인
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6d92cbacba72210c6accbbb1e5ecf25de660fc3c
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730537"
---
# <a name="create-indicators-for-files"></a>파일에 대한 지표 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

잠재적으로 악의적인 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 추가로 전파되는 것을 방지합니다. 잠재적으로 악의적인 PE(이식 가능한 실행 파일) 파일을 알고 있는 경우 해당 파일을 차단할 수 있습니다. 이 작업을 수행하면 조직의 장치에서 읽고 쓰거나 실행할 수 없습니다.

파일에 대한 표시기를 만드는 방법에는 다음 세 가지가 있습니다.

- 설정 페이지를 통해 표시기를 만들어
- 파일 세부 정보 페이지에서 표시기 추가 단추를 사용하여 상황 표시기를 만들 수 있습니다.
- 표시기 API를 통해 [표시기를 만들어](ti-indicator.md)

## <a name="before-you-begin"></a>시작하기 전에

파일에 대한 표시기를 만들기 전에 다음과 같은 선행 방법을 이해하는 것이 중요합니다.

- 이 기능은 조직에서 활성  Microsoft Defender 바이러스 백신 클라우드 기반 보호를 사용하도록 설정된 경우 **사용할 수 있습니다.** 자세한 내용은 클라우드 기반 보호 [관리를 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)

- 맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다. 월별 [플랫폼 및 엔진 버전 참조](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- 2019년 Windows 10 버전 1703 이상, Windows Server 2016 장치에서 지원됩니다.

- 파일 차단을 시작하려면 먼저 파일 차단에서 "차단 또는 [허용"](advanced-features.md) 기능을 켜야 설정.

이 기능은 의심되는 맬웨어(또는 악성 파일)가 웹에서 다운로드되지 않도록 디자인되었습니다. 현재 이식 가능한 PE(실행 파일) 파일(예: 파일 및 .exe 포함).dll 지원됩니다. 적용 범위는 시간이 지날 때 연장됩니다.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>설정 페이지에서 파일에 대한 표시기 만들기

1. 탐색 창에서 **표시기 설정 > 선택합니다.**

2. 파일 **해시 탭을**   선택합니다.

3. 표시기 **추가를 선택합니다.**

4. 다음 세부 정보를 지정합니다.
    - Indicator - 엔터티 세부 정보를 지정하고 표시기 만료를 정의합니다.
    - 작업 - 수행될 작업을 지정하고 설명을 입력합니다.
    - 범위 - 장치 그룹의 범위를 정의합니다.

5. 요약 탭에서 세부 정보를 검토한 다음 저장을 **선택합니다.**

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>파일 세부 정보 페이지에서 상황 표시기 만들기

파일에 대한 응답 [](respond-file-alerts.md)작업을 수행할 때의 옵션 중 하나는 파일에 대한 표시기를   추가하는 것입니다. 파일에 대한 표시기 해시를 추가할 때 조직의 장치가 파일을 실행하려고 할 때마다 경고를 발생하고 파일을 차단할 수 있습니다.

표시기에서 자동으로 차단되는 파일은 파일의 알림 센터에 표시되지 않지만 경고 큐에 계속 표시됩니다.

>[!IMPORTANT]
>- 일반적으로 파일 블록은 몇 분 이내에 적용 및 제거되지만 30분까지 걸릴 수 있습니다.
>- 충돌하는 파일 표시기 정책이 있는 경우 보다 안전한 정책의 적용 정책이 적용됩니다. 예를 들어 두 해시 유형이 동일한 파일을 정의하는 경우 SHA-256 파일 해시 표시기 정책이 MD5 파일 해시 표시기 정책보다 우선합니다.
>- EnableFileHashComputation 그룹 정책을 사용하지 않도록 설정하면 IoC 파일의 차단 정확도가 줄어듭니다. 그러나 EnableFileHashComputation을 사용하도록 설정하면 장치 성능에 영향을 줄 수 있습니다.
>    - 예를 들어 네트워크 공유에서 로컬 장치(특히 VPN 연결을 통해)에 큰 파일을 복사하면 장치 성능에 영향을 미치게 됩니다.
>    - EnableFileHashComputation 그룹 정책에 대한 자세한 내용은 [Defender CSP를 참조하세요.](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>정책 충돌 처리  

Cert 및 File IoC 정책 처리 충돌은 다음 순서를 따르게 됩니다.

- 응용 프로그램 제어 및 AppLocker에서 모드 정책/정책을 Windows Defender 파일을 허용하지 않는 경우 **차단**

- 그 외 제외에서 파일을 Microsoft Defender 바이러스 백신 다음 **허용**

- 그렇지 않은 경우 파일이 차단되거나 파일 IoC에 의해 경고된 경우 **차단/경고**

- 파일을 허용 파일 IoC 정책에서 허용하는 경우  허용

- 다른 경우 파일이 ASR 규칙, CFA, AV, SmartScreen, Block에 의해 **차단된 경우**  

- Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)

적용 유형과 대상이 동일한 충돌하는 파일 IoC 정책이 있는 경우 더 안전한(더 긴) 해시 정책이 적용됩니다. 예를 들어 두 해시 유형이 동일한 파일을 정의하는 경우 SHA-256 파일 해시 IoC 정책이 MD5 파일 해시 IoC 정책에서 이기게 됩니다.

취약한 위협 및 취약성 관리 차단 기능은 적용을 위해 IoC 파일을 사용하며 위의 충돌 처리 순서를 따르게 됩니다.

### <a name="examples"></a>예제

|구성 요소 |구성 요소 적용 |파일 표시기 동작 |결과
|--|--|--|--|
|공격 표면 축소 파일 경로 제외 |허용 |차단 |차단
|공격 표면 감소 규칙 |차단 |허용 |허용
|Windows Defender Application Control |허용 |차단 |허용 |
|Windows Defender Application Control |차단 |허용 |차단
|Microsoft Defender 바이러스 백신 제외 |허용 |차단 |허용

## <a name="see-also"></a>참고 항목

- [지표 만들기](manage-indicators.md)
- [IP 및 URL/도메인에 대한 지표 만들기](indicator-ip-domain.md)
- [인증서를 기반으로 표시기 만들기](indicator-certificates.md)
- [지표 관리](indicator-manage.md)
