---
title: 2단계. 첫 번째 인시던트 수정
description: 2013에서 첫 번째 인시던트 수정을 시작하는 Microsoft 365 Defender.
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
localization_priority: Normal
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
ms.openlocfilehash: 954fa4d9879e9654847f50ad15f8ff3c3a88caf4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213292"
---
# <a name="step-2-remediate-your-first-incident"></a>2단계. 첫 번째 인시던트 수정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

Microsoft 365 Defender 검색 및 분석 기능을 제공하는 것은 물론 맬웨어를 방지하고 제거합니다. 포함에는 공격의 영향을 줄이는 단계가 포함되어 있는 반면, 제거는 공격자 활동의 모든 추적을 네트워크에서 제거합니다.  Microsoft 365 Defender 운영 체제 및 공격 유형에 따라 자동 [](m365d-autoir.md) 수정하도록 구성할 수 있는 몇 가지 수정 작업을 제공합니다.

Microsoft 365 Defender 분석가가 수동으로 시작할 수 있는 여러 가지 수정 작업을 제공합니다. 작업은 디바이스의 작업과 파일에 대한 작업의 두 범주로 구분됩니다. 일부 작업을 사용하여 위협을 즉시 중지하고 다른 작업은 추가 포렌식 분석을 지원할 수 있습니다.

## <a name="actions-on-devices"></a>장치에 대한 작업

- **장치 격리** - 이 활동은 모든 네트워크 트래픽(인터넷 및 내부)을 즉시 차단하여 맬웨어 확산을 최소화하고 악의적인 행위자가 공격을 계속할 수 없는 한 분석가가 분석을 계속할 수 있도록 합니다. 허용되는 유일한 연결은 Id용 Microsoft Defender 서비스 클라우드에 대한 것입니다. 따라서 Id에 대한 Microsoft Defender가 디바이스를 계속 모니터링할 수 있습니다. 
- **앱 실행** 제한 - 응용 프로그램의 실행을 제한하기 위해 Microsoft에서 발급한 인증서로 서명된 파일만 실행할 수 있는 코드 무결성 정책이 적용됩니다. 이 제한 방법은 공격자가 손상된 장치를 제어하고 추가 악의적인 활동을 수행하지 못하게 방지하는 데 도움이 될 수 있습니다.
- **바이러스 백신 검사** 실행 - Microsoft Defender 바이러스 백신 바이러스 백신이 활성 바이러스 백신 솔루션인지 여부에 따라 다른 바이러스 백신 솔루션과 함께 검사가 실행될 수 있습니다. 다른 바이러스 백신 공급업체 제품이 기본 끝점 보호 솔루션인 경우 수동 모드에서 Defender 바이러스 백신을 실행할 수 있습니다.
- **자동화된 조사 시작** - 장치에서 새로운 일반 목적의 자동화된 조사를 시작할 수 있습니다. 조사가 실행되는 동안 장치에서 생성된 다른 모든 경고는 해당 조사가 완료될 때까지 진행 중인 자동화된 조사에 추가됩니다. 또한 다른 장치에서 동일한 위협이 있는 경우 해당 장치가 조사에 추가됩니다.
- **실시간 응답** 시작 - 실시간 응답은 원격 셸 연결을 사용하여 장치에 즉시 액세스할 수 있는 기능입니다. 이를 통해 심층 조사 작업을 수행하고 즉각적인 대응 조치를 취하여 식별된 위협을 실시간으로 즉시 포함할 수 있습니다. 실시간 대응은 사용자가 법의적 데이터를 수집하고, 스크립트를 실행하고, 분석을 위해 의심스러운 엔터티를 보내고, 위협을 수정하고, 새로운 위협에 대한 사전 대응적 헌팅을 할 수 있도록 하여 조사를 강화하도록 고안된 것입니다.
- **조사 패키지 수집** - 조사 또는 응답 프로세스의 일부로 장치에서 조사 패키지를 수집할 수 있습니다. 조사 패키지를 수집하면 장치의 현재 상태를 식별하고 공격자가 사용하는 도구와 기술을 추가로 이해할 수 있습니다. 
- **위협 전문가(장치** 및 파일에 대한 작업 모두에서 사용 가능) - Microsoft 위협 전문가에게 이미 손상된 장치 또는 잠재적으로 손상된 장치에 대한 자세한 정보를 얻을 수 있습니다. Microsoft 위협 전문가는 시기적용하고 정확한 대응을 위해 Microsoft Defender 보안 센터 직접 참여할 수 있습니다. 

## <a name="actions-on-files"></a>파일에 대한 작업

- 파일 중지 및 **Quarantine** - 이 작업으로는 실행 중인 프로세스를 중지하고, 파일을 검지하고, 레지스트리 키와 같은 영구 데이터를 삭제하는 작업이 포함됩니다. 이 작업은 지난 30일 동안 Windows 10 버전 1703 이상이 있는 장치에 적용됩니다. 
- **파일을 차단하거나** 허용하는 표시기 추가 - 잠재적으로 악의적인 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 더 이상 전파되지 않도록 합니다. 이 작업을 수행하면 조직의 장치에서 파일을 읽거나 쓰거나 실행할 수 없습니다.
- **파일 다운로드** 또는 수집 - 이 작업을 통해 분석가가 암호로 보호된 파일 보관 파일로 파일을 .zip 추가 분석을 위해 파일을 다운로드할 수 있습니다.
- **심층 분석** - 이 작업은 안전하고 완벽하게 계측된 클라우드 환경에서 파일을 실행합니다. 심층 분석 결과에는 파일의 활동, 관찰된 동작 및 연결된 아티팩트(예: 삭제된 파일, 레지스트리 수정, IP 주소와의 통신)가 표시됩니다. 

인시던트 [감지,](first-incident-analyze.md#analyze-your-first-incident)분석 및 분석의 예제를 계속 진행하면 분석가가 다음 작업을 사용하여 이 인시던트를 재구성할 수 있습니다.

1. 사용자 계정 암호 즉시 다시 설정
2. 심층 분석이 Microsoft 365 Defender 장치 격리
3. 악의적인 파일이 해당 파일에서 SharePoint
4. 맬웨어의 영향을 받은 끝점 확인
5. 시스템 다시 구성
6. 다른 사용자에 대한 Microsoft Cloud App Security 경고 확인
7. 끝점용 Microsoft Defender에서 Tor IP 주소를 차단하는 사용자 지정 표시기 만들기
8. 다음 이미지에 Microsoft Cloud App Security 이러한 유형의 경고에 대한 거버넌스 작업을 만듭니다.

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="사이트 포털의 거버넌스 Microsoft Cloud App Security 예입니다."::: 
 
대부분의 수정 작업은 작업에서 적용하고 추적할 수 Microsoft 365 Defender. 

## <a name="using-playbooks"></a>Playbook 사용

또한 playbook을 사용하여 자동화된 수정을 만들 수 있습니다. 현재 [Microsoft에는](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) 다음과 같은 시나리오에 GitHub 플레이북을 제공하는 Playbook 템플릿이 있습니다.

- 사용자 유효성 검사를 요청한 후 중요한 파일 공유 제거
- 소수의 국가 자동 세분화 경고
- 계정을 사용 안 하게 하기 전에 관리자 작업 요청
- 악의적인 받은 편지함 규칙을 사용하지 않도록 설정

플레이북은 Power Automate 트리거되면 사용자 지정 로봇 프로세스 자동화 흐름을 만들어 특정 활동을 자동화합니다. 조직은 기존 템플릿에서 또는 처음부터 플레이북을 만들 수 있습니다. 

다음은 예입니다.
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="사용자 지정 Power Automate 자동화 흐름의 예입니다."::: 
 
인시던트 사후 [](first-incident-post.md) 검토 중에 Playbook을 만들어 더 빠른 수정 작업을 위해 인시던트에서 수정 작업을 만들 수도 있습니다. 

## <a name="next-step"></a>다음 단계

[![3단계: 인시던트에 대한 인시던트 사후 검토를 수행하는 방법을 배워야 합니다.](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)

인시던트에 [대한 인시던트 사후](first-incident-post.md)검토를 수행하는 방법을 학습합니다.

## <a name="see-also"></a>참고 항목

- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)
