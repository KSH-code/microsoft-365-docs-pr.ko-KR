---
title: Microsoft Defender for Office 365를 사용하여 피싱 공격 시뮬레이션
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 관리자는 Microsoft Defender for Office 365의 공격 시뮬레이션 교육을 사용하여 피싱 공격을 시뮬레이션하고 사용자를 피싱 방지에 교육하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 3707041067fd76ee9535d0dccf5cdfcb9d74fbd7
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667582"
---
# <a name="simulate-a-phishing-attack"></a>피싱 공격 시뮬레이션

Office 365용 Microsoft Defender의 공격 시뮬레이터 교육을 통해 조직에서 양성 사이버 공격 시뮬레이션을 실행하여 보안 정책 및 관행을 테스트하고 직원의 인식을 높이고 공격에 대한 인식을 낮출 수 있도록 교육할 수 있습니다. 이 문서에서는 공격 시뮬레이터 교육을 사용하여 시뮬레이트된 피싱 공격을 만드는 방법을 연습합니다.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

시뮬레이션된 피싱 공격을 시작하기 위해 [Microsoft 365](https://security.microsoft.com/)보안  센터를 열고 전자 메일 & 공격 시뮬레이터로 이동한 다음 시뮬레이션 탭으로 \> 전환합니다. [](https://security.microsoft.com/attacksimulator?viewid=simulations)

**시뮬레이션에서**+ **시뮬레이션 실행을 선택합니다.**

![Microsoft 365 보안 센터에서 시뮬레이션 단추 시작](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> 시뮬레이션을 만들 때 어느 시점에서든 저장 후 닫아서 나중에 시뮬레이션을 계속 구성할 수 있습니다.

## <a name="selecting-a-social-engineering-technique"></a>소셜 엔지니어링 기술 선택

[MITRE ATT 및 CK&](https://attack.mitre.org/techniques/enterprise/)프레임워크에서 ® 선택합니다. 다양한 기술에 대해 다양한 페이로드를 사용할 수 있습니다.

- **자격 증명 수집은** 입력란이 있는 잘 알려진 웹 사이트로 사용자를 연결하여 사용자 이름 및 암호를 제출하여 자격 증명을 수집하려고 시도합니다.
- **맬웨어 첨부** 파일은 메시지에 악성 첨부 파일을 추가합니다. 사용자가 첨부 파일을 열면 공격자가 대상의 장치를 손상시킬 수 있도록 임의의 코드가 실행됩니다.
- **첨부 파일 링크는** 자격 증명 수집 하이브리드의 한 유형입니다. 공격자는 전자 메일 첨부 파일에 URL을 삽입합니다. 첨부 파일 내의 URL은 자격 증명 수집과 동일한 기술을 따르게 됩니다.
- **맬웨어에 대한** 링크는 잘 알려진 파일 공유 서비스에 호스트된 파일에서 일부 임의 코드를 실행합니다. 사용자에게 전송된 메시지에는 이 악성 파일에 대한 링크가 포함되어 있습니다. 파일을 열고 공격자가 대상의 장치를 손상시킬 수 있도록 합니다.

> [!TIP]
> 각 기술에 **대한** 설명 내에서 세부 정보 보기를 클릭하면 해당 기술에 대한 추가 정보와 시뮬레이션 단계가 표시됩니다.
>
> ![Microsoft 365 보안 센터의 공격 시뮬레이션 교육 내에서 자격 증명 수집을 위한 시뮬레이션 단계](../../media/attack-sim-preview-sim-steps.png)

기술을 선택한 후 다음을 클릭한 후 **시뮬레이션에** 이름과 설명(선택 사항)을 지정합니다.

## <a name="selecting-a-payload"></a>페이로드 선택

다음으로 기존 페이로드 카탈로그에서 페이로드를 선택해야 합니다.

페이로드에는 다음을 선택하는 데 도움이 되는 다양한 데이터 포인트가 있습니다.

- **클릭 속도는** 이 페이로드를 클릭한 사용자 수를 계산합니다.
- **예측된** 손상율은 Office 365 고객용 Microsoft Defender의 페이로드에 대한 기록 데이터를 기반으로 이 페이로드에 의해 손상되는 비율을 예측합니다.
- **실행된 시뮬레이션은** 이 페이로드가 다른 시뮬레이션에 사용된 횟수를 계산합니다.
- **필터를** **통해** 사용할 수 있는 복잡성은 페이로드 내의 지표 수를 기반으로 계산됩니다. 페이로드에서 공격 대상의 단서가 되는 지표 수를 기반으로 계산됩니다. 표시기가 수록 복잡성이 낮아집니다.
- **필터를** **통해** 사용할 수 있는 원본은 페이로드가 테넌트에서 만들어지거나 Microsoft의 기존 페이로드 카탈로그(전역)의 일부인지 여부를 나타냅니다.

![Microsoft 365 보안 센터의 공격 시뮬레이션 교육 내에서 선택한 페이로드](../../media/attack-sim-preview-select-payload.png)

목록에서 페이로드를 선택하여 해당 페이로드에 대한 추가 정보가 있는 페이로드의 미리 보기를 볼 수 있습니다.

자신만의 페이로드를 만들고자 하는 경우 공격 시뮬레이션 교육을 위한 [페이로드를 만드시다.](attack-simulation-training-payloads.md)

## <a name="audience-targeting"></a>대상 그룹 지정

이제 이 시뮬레이션의 대상을 선택해야 합니다. 조직의 모든  사용자를 포함하거나 특정 사용자 및 그룹만 **포함하도록 선택할 수 있습니다.**

특정 사용자 및 그룹만 **포함하도록** 선택하는 경우 다음 중 하나를 사용할 수 있습니다.

- **지난** 3개월 동안 시뮬레이션의 대상으로 지정되지 않은 사용자를 대상으로 지정하는 등 고급 검색 및 필터링 기능뿐만 아니라 테넌트에 대한 검색을 활용할 수 있는 사용자를 추가합니다.
  ![Microsoft 365 보안 센터의 공격 시뮬레이션 교육에서 사용자 필터링](../../media/attack-sim-preview-user-targeting.png)
- **CSV에서 가져오기 기능을 사용하면** 이 시뮬레이션을 위해 미리 정의한 사용자 집합을 가져올 수 있습니다.

## <a name="assigning-training"></a>교육 할당

교육을 진행하는 직원은 유사한 공격에 덜 덜 덜 공격하기에 각 시뮬레이션에 대한 교육을 할당하는 것이 좋습니다.

교육을 할당하거나 직접 교육 과정과 모듈을 선택할 수 있습니다.

교육 **기한을 선택하여** 직원들이 제시간에 교육을 완료할 수 있도록 합니다.

> [!NOTE]
> 직접 과정과 모듈을 선택하려면 권장되는 콘텐츠와 사용 가능한 모든 과정 및 모듈을 볼 수 있습니다.
>
> ![Microsoft 365 보안 센터의 공격 시뮬레이션 교육 내에서 권장 교육 추가](../../media/attack-sim-preview-add-training.png)

다음 단계에서 직접 교육을  선택하기로 선택한 경우 교육을 추가하고 교육 방문 페이지를 사용자 지정해야 합니다. 교육 방문 페이지를 미리 볼 수 있을 뿐만 아니라 머리더와 본문도 변경할 수 있습니다.

## <a name="launch-details-and-review"></a>시작 세부 정보 및 검토

이제 모든 것이 구성되면 이 시뮬레이션을 즉시 시작하거나 나중에 예약할 수 있습니다. 또한 이 시뮬레이션을 종료할 때를 선택해야 합니다. 선택한 시간을 지난 후 이 시뮬레이션의 조작 캡처를 중지합니다.

**지역 인식 시간 표시** 시간 배달을 사용하도록 설정하여 해당 지역에 따라 작업 시간 동안 시뮬레이트된 공격 메시지를 직원에게 전달합니다.

완료되면 다음을 클릭하고  시뮬레이션의 세부 정보를 검토합니다. 편집을  클릭하여 돌아가서 변경해야 하는 세부 정보를 변경합니다. 완료되면 제출을 **클릭합니다.**
