---
title: Microsoft Managed Desktop 수명 주기
description: 이 문서에서는 디바이스 사양에 사용되는 장치 사양을 Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: df9bf273edd85fea08cd11838093a1287b0fff97
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215372"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop 수명 주기

> [!NOTE]
> 2021년 9월 18일부로, 이 제품 수명 주기는 Microsoft Managed Desktop 않습니다. 여기에 나열된 요구 사항은 서비스의 장치에 적용되지 않습니다. 하드웨어 [요구 사항만](device-requirements.md) 관련이 있습니다. 


Microsoft Managed Desktop, 안정성, 디자인 및 보안 기능(예: Windows Hello)을 제공하는 장치를 항상 사용하게 하여 사용자에게 Windows Hello. 이를 위해 Microsoft Managed Desktop 업데이트된 장치의 짧은 카탈로그를 유지 관리합니다. 비즈니스 디바이스 쇼핑 사이트에서 승인된 Microsoft Managed Desktop [필터링하여 Windows 10 Pro 수](https://www.microsoft.com/en-us/windowsforbusiness/view-all-devices) 있습니다.
 
이 문서에서는 디바이스가 승인된 카탈로그에서 추가 및 제거될 때의 장치 수명 주기에 대해 자세히 소개합니다. 

> [!NOTE]
> 이 항목에서는 "장치"와 "제품"을 구분합니다. "장치"는 하나의 개별적인 특정 컴퓨터를 의미합니다. 예를 들어 "일련 번호 1234", "청구서 노트북", "공유 VM XYZ"는 특정 장치를 참조합니다. 그러나 "제품"은 디바이스의 컬렉션 또는 패밀리를 참조합니다. 예를 들어 "Fabrikam Laptop", "Adatum ZX450 Laptop" 등이 있습니다. 이는 제품이 승인된 목록 또는 카탈로그에 추가되는 것이고 장치가 해당 목록에 등록되는 Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>제품 수명 주기

 일반적으로 제품은 이러한 수명 주기 단계를 통해 이동됩니다.

- [제품 릴리스 및 평가](#product-release-and-evaluation)
- [제품 기본 가용성 기간](#product-primary-availability-period)
- [제품 유예 기간](#product-grace-period)
- [제품 사용 중지](#product-retirement)


이 그림은 전체 시퀀스를 보여 주며,

![수명 주기 타임라인: 제품 일반 공급으로 시작하여 "기본 가용성"은 2년 동안 지속됩니다. 이 시간 동안 인증 창이 종료된 후 디바이스가 온보더된 시점에 종료됩니다. 기본 가용성이 끝나면 제품이 보관된 후 3년의 "유예 기간"이 시작됩니다. 디바이스가 온보드될 때부터 관리에서 제거될 때까지 3년의 사용 기간이 있습니다. 유예 기간이 끝나면 카탈로그에서 제품을 제거합니다.](../../media/non-dark1-edits.PNG)

제품은 최대 24개월 동안 카탈로그에 남아 <em></em> 있지만 장치는 개별 등록 날짜에 따라 3년 동안 관리되지 않습니다. 효과적으로 각 제품에는 세 개의 중요한 날짜가 있지만 각 장치에는 하나의 날짜만 있습니다. 제품의 경우 이러한 세 날짜 모두 승인 <em></em>날짜에 따라 계산됩니다. 따라서 승인 시 이러한 날짜를 게시하여 제품의 전체 수명 주기에 대해 항상 적절하게 계획할 수 있습니다.

다음 표에서는 다음과 같은 예시적 제품의 날짜를 보여 주며,


|제품  |승인된 날짜  |기본 가용성 종료  |자격 종료  |
|---------|---------|---------|---------|
|Fabrikam 노트북    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum 노트북   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

다음 표에는 예시의학적 장치 날짜가 *표시됩니다.*


|장치 ID  |등록 날짜  |사용 중지 날짜  |
|---------|---------|---------|
|노트북 #123412     |  2/3/2018       |  2/3/2021       |
|데스크톱 #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>제품 릴리스 및 평가

제조업체가 제품을 공개적으로 릴리스하면 제품 수명 주기가 시작됩니다.

![수명 주기 타임라인에 릴리스 및 평가 기간이 표시됩니다.](../../media/non-dark3-edits.PNG)

이 단계에서는 Microsoft Managed Desktop 엔지니어링 팀이 제품의 평가 및 인증을 진행합니다. 이 팀은 특히 Windows 안정성 및 성능, 하드웨어 기준 준수, 시장 정서, 인벤토리 및 채널 준비를 평가합니다. 이 프로세스는 일반적으로 약 6주가 소요됩니다.
  
Microsoft Managed Desktop 처음 6개월 이내에 인증을 위한 장치만 평가합니다. 이 정책은 항상 최신 하드웨어 세대에 노력을 집중하고 있습니다.
 
이 단계가 끝나면 Microsoft Managed Desktop 목록에 제품을 추가하여 [](device-list.md)고객 등록을 위해 제품을 효과적으로 출시합니다. 장치가 인증된 날짜와 관계없이 승인된  날짜는 제품의 일반 공급 날짜로 다시 날짜가 정해진 날짜입니다. 


## <a name="product-primary-availability-period"></a>제품 기본 가용성 기간

이 기간은 제품 가용성의 핵심입니다.

![기본 가용성을 보여주는 수명 주기 타임라인입니다.](../../media/non-dark4-edits.PNG)

이 기간 동안 등록된 모든 디바이스는 파란색 타임라인에 표시된 Microsoft Managed Desktop 3년의 전체 지원을 받게 됩니다. 이 기간은 종료 날짜가 일반 공급 날짜로부터 24개월로 설정될 때까지 지속됩니다.

이 기간을 효과적으로 "개방형 등록"으로 생각할 수 있으므로 Microsoft Managed Desktop 해당 기간 내에 사용할 조달 모델 및 선택한 제품을 대상으로 지정해야 합니다. 작은 예로, 기본 가용성의 마지막 달에 있는 제품을 사용하여 2년의 롤아웃 기간에 대한 정착을 피해야 합니다. 이러한 장치는 대부분 3년 동안의 Microsoft Managed Desktop 관리(자세한 내용은 유예 기간 참조)를 받지 못합니다. [](#product-grace-period)  

## <a name="product-grace-period"></a>제품 유예 기간

제품 유예 기간은 기본 가용성 이후 3년의 기간입니다. 이 단계를 통해 지원되는 제품 패밀리의 장치를 등록할 수 있지만 최신 하드웨어 및 장치 성능과 관련하여 Microsoft Managed Desktop 약속을 지키고 있습니다. 이 단계는 조달 결정을 내렸다가 구매 정보를 알고 있는 고객에게 Microsoft Managed Desktop. 

Microsoft Managed Desktop 등록하기 전에 최근에 승인된 장치를 구입한 경우 등록할 수 있지만 3년 동안의 관리는 받지 못합니다. 대신 등록한 날짜와 관계없이 사용 중지 날짜에 규정을 준수하지 않습니다. 숨은 Microsoft Managed Desktop 기본 가용성의 마지막 날에 등록된 장치처럼 이러한 장치를 처리합니다. 이 그림에서는 등록이 1년의 차이에도 불구하고 파란색 및 녹색 장치가 같은 날에 종료됩니다.


![유예 기간을 표시하는 수명 주기 타임라인입니다.](../../media/non-dark2-edits.PNG)

이전 표의 Fabrikam 노트북 예제에서는 이러한 상황을 보여 주었다. 

|제품  |승인된 날짜  |기본 가용성 종료  |자격 종료  |
|---------|---------|---------|---------|
|Fabrikam 노트북    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

고객은 2022년 6월 1일까지 Fabrikam 랩톱을 등록할 수 있습니다. 그러나 Fabrikam 노트북은 모두 2019년 6월 1일에 등록한 것으로 간주됩니다. 2021년 6월 1일에 Fabrikam 노트북을 등록하는 경우 1년의 관리만 받을 수 있습니다. 이 정책을 사용하면 새 장치를 조달하지 않고도 이전에 지원했던 제품에서 부분 수명 주기를 추출할 수 있습니다. 

마지막으로, 이 단계에서 장치는 장치 목록에서 제거되고 보관된 장치 [목록으로 이동됩니다.](archived-device-list.md) [](device-list.md)


## <a name="product-retirement"></a>제품 사용 중지

제품 사용 중지는 수명 주기의 마지막 단계입니다. 이 단계에서는 해당 제품 유형의 새 장치를 등록할 수 Microsoft Managed Desktop 정의에 따라 모든 기존 장치가 이제 허용된 3년 기간을 밖으로 합니다. 이 시간 동안 Microsoft Managed Desktop 디바이스를 공개 목록에서 완전히 제거합니다. 또한 이 단계에서는 아직 교체를 조달하지 않은 경우, Microsoft Managed Desktop 장치가 규정을 준수하지 않는 디바이스에서 램프다운을 시작하면 서비스 수가 밝아지기 시작합니다. 

## <a name="devices-that-are-out-of-compliance"></a>규정을 준수하지 않습니다.

장치 관리에 허용된 창이 경과하면 장치가 Microsoft Managed Desktop 않습니다. 이러한 상황은 장치가 3년의 관리에 도달하거나 해당 제품 유형이 장치 카탈로그에서 제거될 때 가장 먼저 발생합니다. 항상 조달 주기를 대상으로 하여 현재 장치가 규정을 준수하지 않을 수 있도록 새 장치를 배포해야 합니다.

Microsoft Managed Desktop 팀에서는 조달 주기가 길고 장기 실행 예산에 대한 계획된 것을 알고 있습니다. 장치 인구의 상태를 항상 인식할 수 있도록 관리의 [](https://aka.ms/mmdportal) 모든 장치, 해당 연령 및 규정 준수를 나타내는 상태를 나열하는 웹 사이트를 제공합니다. 이 웹 사이트는 장치 사용에 대한 최신 정보를 항상 확보할 수 있으며 모든 조달 계획 주기에서 보고서를 사용할 수 있습니다. 







