---
title: 커뮤니케이션 규정 준수 정책
description: 통신 규정 준수 정책에 대해 자세히 알아보면 됩니다.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 96cce3c715cb282db2ce1718440b13e43f5145b6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60702052"
---
# <a name="communication-compliance-policies"></a>커뮤니케이션 규정 준수 정책

## <a name="policies"></a>정책

> [!IMPORTANT]
> PowerShell을 사용하여 커뮤니케이션 규정 준수 정책을 만들고 관리하는 것은 지원되지 않습니다. 이러한 정책을 만들고 관리하려면 통신 규정 준수 솔루션의 정책 관리 [Microsoft 365 합니다.](https://compliance.microsoft.com/supervisoryreview)

Microsoft 365 규정 준수 센터에서 Microsoft 365 조직에 대한 커뮤니케이션 규정 준수 정책을 만들 수 있습니다. 통신 준수 정책은 조직에서 검토할 통신 및 사용자를 정의하고, 통신이 충족해야 하는 사용자 지정 조건을 정의하고, 검토할 사용자를 지정합니다. 통신 준수 *관리자 역할이* 할당된 사용자는 정책을 설정할 수 있으며,  이 역할이 할당된 모든 사용자는 정책의 통신 준수 페이지 및 전역 설정에 액세스할 Microsoft 365 규정 준수 센터. 필요한 경우 정책 수정 내역을 검토 보류 중인 알림.csv 에스컬레이터된 항목 및 해결된 항목의 상태도 포함하는 정책(콤보로 구분된 값) 파일로 내보낼 수 있습니다. 정책의 이름을 바을 수 없습니다. 더 이상 필요하지 않은 경우 삭제할 수 있습니다.

## <a name="policy-templates"></a>정책 템플릿

정책 템플릿은 일반적인 규정 준수 시나리오를 해결하기 위한 정책을 신속하게 만드는 데 사용할 수 있는 미리 정의된 정책 설정입니다. 이러한 각 템플릿은 조건과 범위의 차이를 가지며, 모든 템플릿은 동일한 유형의 검색 신호를 사용 합니다. 다음 정책 템플릿 중 선택할 수 있습니다.

|**영역**|**정책 템플릿**|**세부 정보**|
|:-----|:-----|:-----|
| **부적절한 콘텐츠** | 부적절한 콘텐츠에 대한 통신 모니터링 | - 위치: Exchange Online, Microsoft Teams, Yammer, 비즈니스용 Skype <br> - 방향: 인바운드, 아웃바운드, 내부 <br> - 검토 비율: 100% <br> - 조건: 위협, 괴롭음, 대상 괴롭음, 성인용 이미지, 인종 이미지 및 고리 이미지 분류자 |
| **민감 정보** | 중요한 정보에 대한 통신 모니터링 | - 위치: Exchange Online, Microsoft Teams, Yammer, 비즈니스용 Skype <br> - 방향: 인바운드, 아웃바운드, 내부 <br> - 검토 비율: 10% <br> - 조건: 중요한 정보, 첫 번째 콘텐츠 패턴 및 유형, 사용자 지정 사전 옵션, 1MB보다 큰 첨부 파일 |
| **규정 준수** | 금융 규제 준수와 관련된 정보 통신 모니터링 | - 위치: Exchange Online, Microsoft Teams, Yammer, 비즈니스용 Skype <br> - 방향: 인바운드, 아웃바운드 <br> - 검토 비율: 10% <br> - 조건: 사용자 지정 사전 옵션, 1MB보다 큰 첨부 파일 |
| **이해 상충** | 두 그룹 또는 두 사용자 간의 통신을 모니터링하여 이해 상충 방지 | - 위치: Exchange Online, Microsoft Teams, Yammer, 비즈니스용 Skype <br> - 방향: 내부 <br> - 검토 비율: 100% <br> - 조건: 없음 |

통신은 정책이 만들어진 시간부터 24시간마다 검색됩니다. 예를 들어 오전 11시에 부적절한 콘텐츠 정책을 만드는 경우 정책은 매일 오전 11시에 24시간마다 통신 준수 신호를 수집합니다. 이번에는 정책을 편집해도 변경되지 않습니다. 정책에 대한 마지막 검사 날짜 및 시간을 표시하기 위해 정책 페이지의 마지막 정책 *검사* **열로 이동합니다.** 새 정책을 만들고 나면 첫 번째 정책 검사 날짜 및 시간을 보는 데 최대 24시간이 걸릴 수 있습니다. 마지막 검사의 날짜와 시간은 로컬 시스템의 표준 시간대로 변환됩니다.

## <a name="pause-a-policy-preview"></a>정책 일시 중지(미리 보기)

통신 준수 정책을 만든 후 필요한 경우 해당 정책이 일시적으로 일시 중지될 수 있습니다. 정책의 상태 변경은 정책 일치를 테스트 또는 문제 해결하거나 정책 조건을 최적화하는 데 사용될 수 있습니다. 이러한 상황에서 정책을 삭제하는 대신 정책을 페이스할 경우 지속적인 조사 및 검토를 위한 기존 정책 경고 및 메시지도 보존됩니다. 정책을 일시 중지하면 정책이 일시 중지된 시간 동안 정책에 정의된 모든 사용자 메시지 조건에 대한 검사 및 경고 생성을 방지할 수 있습니다. 정책을 일시 중지하거나 다시 시작하려면 사용자가 *Communication Compliance Admin* 역할 그룹의 구성원이 되어야 합니다.

정책을 일시 중지하려면 정책 페이지로 **이동하여** 정책을 선택한  다음 작업 도구 모음에서 정책 일시 중지를 선택합니다. 정책 **일시 중지 창에서** 일시 중지 를 선택하여 정책을 일시 중지할지 **선택합니다.** 경우에 따라 정책을 일시 중지하는 데 최대 24시간이 걸릴 수 있습니다. 정책이 일시 중지되면 정책과 일치하는 메시지에 대한 알림이 생성되지 않습니다. 그러나 정책을 Pausing하기 전에 만든 경고와 관련된 메시지는 조사, 검토 및 수정을 위해 계속 사용할 수 있습니다.

일시 중지된 정책의 정책 상태는 여러 상태를 나타낼 수 있습니다.

- **활성:** 정책이 활성 상태입니다.
- **일시 중지:** 정책이 완전히 일시 중지됩니다.
- **일시 중지:** 정책이 일시 중지 중입니다.
- **다시 시작:** 다시 시작되는 프로세스의 정책입니다.
- **다시 시 오류:** 정책을 다시할 때 오류가 발생했습니다. 오류 스택 추적의 경우 정책 페이지의 상태 열에서 상태를 다시 열 때 *오류* 위에 마우스를 놓습니다.
- **지연 오류:** 정책을 페이스할 때 오류가 발생했습니다. 오류 스택 추적의 경우 정책 페이지의 상태 열에서 상태를 페이스할 때 *오류* 위에 마우스를 놓습니다.

정책을 다시 시작하려면 정책 페이지로 **이동하여** 정책을 선택한  다음 작업 도구 모음에서 정책 다시 시작을 선택합니다. 정책 **다시 시작** 창에서 다시 시작 을 선택하여 정책을 다시 시작할지 **선택합니다.** 경우에 따라 정책을 다시 시작하는 데 최대 24시간이 걸릴 수 있습니다. 정책이 다시 시작되면 정책과 일치하는 메시지에 대한 알림이 만들어지며 조사, 검토 및 수정에 사용할 수 있습니다.

## <a name="copy-a-policy-preview"></a>정책 복사(미리 보기)

기존 통신 준수 정책이 있는 조직의 경우 기존 정책에서 새 정책을 만드는 시나리오가 유용할 수 있습니다. 정책을 복사하면 모든 범위 내 사용자, 할당된 모든 검토자 및 모든 정책 조건을 포함하여 기존 정책이 정확히 중복됩니다. 일부 시나리오는 다음과 같습니다.

- **정책 저장소 제한에 도달했습니다.** 활성 통신 준수 정책에는 메시지 저장소 제한이 있습니다. 정책의 저장소 제한에 도달하면 정책이 자동으로 비활성화됩니다. 비활성화된 정책에서 다루는 부적절한 메시지를 계속 검색, 캡처 및 작업해야 하는 조직은 동일한 구성을 사용하여 새 정책을 빠르게 만들 수 있습니다.
- **여러 사용자** 그룹에 대한 부적절한 메시지를 검색하고 검토: 일부 조직에서는 구성이 동일하지만 범위 내 사용자와 각 정책에 대해 서로 다른 검토자는 포함하기를 원할 수 있습니다.
- **작은 변경 내용이 있는** 유사한 정책: 복잡한 구성 또는 조건이 있는 정책의 경우 유사한 정책에서 새 정책을 만드는 데 시간을 절약할 수 있습니다.

정책을 복사하려면 사용자가 통신 준수 또는  통신 준수 관리자 역할 그룹의 *구성원이* 되어야 합니다. 기존 정책에서 새 정책을 만든 후 새 정책 구성과 일치하는 메시지를 보는 데 최대 24시간이 걸릴 수 있습니다.

정책을 복사하고 새 정책을 만들 수 있는 경우 다음 단계를 완료합니다.

1. 복사할 정책을 선택합니다.
2. 명령 **표시줄에서** 정책 명령 표시줄  단추 복사를 선택하거나 정책에 대한 작업 메뉴에서 정책 복사를 선택합니다.
3. 정책 **복사 창의** 정책 이름 필드에서 정책의 기본  이름을 수락하거나 정책 이름을 변경합니다. 새 정책의 정책 이름은 기존 활성 정책 또는 비활성화된 정책과 같을 수 없습니다. 필요한 경우 **설명 필드를** 입력합니다.
4. 정책을 추가로 사용자 지정하지 필요 없는 경우  정책 복사를 선택하여 프로세스를 완료합니다. 새 정책의 구성을 업데이트해야 하는 경우 정책 사용자 **지정 을 선택합니다.** 그러면 새 정책을 업데이트하고 사용자 지정하는 데 도움이 되는 정책 마법사가 시작됩니다.

## <a name="storage-limit-notification-preview"></a>Storage 제한 알림(미리 보기)

각 통신 준수 정책의 저장소 제한 크기는 100GB 또는 100만 개 메시지 중 먼저 도달하는 메시지입니다. 정책이 이러한 제한에 도달하면 알림 전자 메일이 통신  준수 또는 통신 준수 관리자 역할 그룹에 할당된 사용자에게 *자동으로* 전송됩니다. 저장소 크기 또는 메시지 수가 제한의 80%, 90% 및 95%에 도달하면 알림 메시지가 전송됩니다. 정책 제한에 도달하면 정책이 자동으로 비활성화되고 정책이 경고에 대한 메시지 처리를 중지합니다.

>[!IMPORTANT]
>저장소 및 메시지 제한에 도달하여 정책이 비활성화된 경우 비활성화된 정책을 관리하는 방법을 평가해야 합니다. 정책을 삭제하면 모든 메시지, 연결된 첨부 파일 및 메시지 알림이 영구적으로 삭제됩니다. 이러한 항목을 유지 관리해야 하는 경우 비활성화된 정책을 삭제하지 않습니다.

저장소 및 메시지 제한에 접근하는 정책을 관리하기 위해 정책 복사본을 만들어 적용 범위 연속성을 유지하거나 다음 작업을 수행하여 현재 정책 저장소 크기 및 메시지 수를 최소화하는 데 도움이 됩니다.

- 정책에 할당된 사용자 수를 줄이는 것이 고려됩니다. 정책에서 사용자를 제거하거나 여러 사용자 그룹에 대해 서로 다른 정책을 만들면 정책 크기 및 총 메시지의 증가 속도를 늦출 수 있습니다.
- 정책을 검사하여 과도한 가짓 긍정 경고를 검사합니다. 일반적인 가짓 긍정 경고를 무시하기 위해 정책 조건에 예외 또는 변경 내용을 추가하는 것을 고려합니다.
- 정책이 저장소 또는 메시지 제한에 도달하고 비활성화된 경우 정책 복사본을 만들어 동일한 조건과 사용자에 대한 작업을 계속 감지하고 조치를 취합니다.

## <a name="policy-settings"></a>정책 설정

### <a name="users"></a>사용자

모든 사용자를 **선택하거나** 통신 준수 정책에서 특정 사용자를 정의하도록 선택할 수 있습니다. **모든 사용자** 를 선택하면 모든 사용자 및 각 사용자가 구성원으로 포함된 모든 그룹에 정책이 적용됩니다. 특정 사용자를 정의하면, 정의된 사용자 및 해당 사용자가 구성원으로 포함된 각 그룹에 정책이 적용됩니다.

### <a name="direction"></a>방향

기본적으로 **Direction는** 조건이 표시되고 제거할 수 없습니다. 정책의 통신 방향 설정은 개별적으로 또는 함께 선택됩니다.

- **인바운드:** 정책의  다른 감독된 사용자를 포함하여 외부 및 내부 보낸 사람이 감독하는 사용자에게 전송된 통신을 검색합니다.
- **아웃바운드**: 정책의 다른 감독된 사용자를 포함하여 감독되는 사용자가 외부 및 내부 받는 사람에게 보낸 통신을 검색합니다. 
- **내부:** 정책의  감독된 사용자 또는 그룹 간의 통신을 검색합니다.

### <a name="sensitive-information-types"></a>중요한 정보 유형

커뮤니케이션 규정 준수 정책의 일부로 중요한 정보 유형을 포함하도록 선택할 수 있습니다. 중요한 정보 유형은 신용 카드 번호, 은행 계좌 번호, 여권 번호 등 식별하고 보호하는 데 도움이 되는 미리 정의된 데이터 형식 또는 사용자 지정 데이터 형식입니다. 데이터 손실 방지에 대한 정보의 일부로 [중요한](dlp-learn-about-dlp.md)정보 구성은 패턴, 문자 근접성, 신뢰 수준 및 사용자 지정 데이터 형식을 사용하여 중요한 콘텐츠를 식별하고 플래그를 지정하는 데 도움이 될 수 있습니다. 기본 중요한 정보 유형은 다음입니다.

- 금융
- 의료 및 건강
- 개인 정보
- 사용자 지정 정보 유형

중요한 정보 세부 정보 및 기본 유형에 포함된 패턴에 대한 자세한 내용은 중요한 정보 유형 엔터티 정의 [를 참조하세요.](sensitive-information-type-entity-definitions.md)

### <a name="custom-keyword-dictionaries"></a>사용자 지정 키워드 사전

조직 또는 산업 관련 키워드를 간단하게 관리하도록 사용자 지정 키워드 사전(또는 사전)을 구성합니다. 키워드 사전은 사전에서 최대 100 KB의 용어(압축 후)를 지원하고 모든 언어를 지원합니다. 또한 테넌트 제한은 압축 후 100 KB입니다. 필요한 경우 단일 정책에 여러 사용자 지정 키워드 사전을 적용하거나 정책당 단일 키워드 사전을 사용할 수 있습니다. 이러한 사전은 통신 준수 정책에 할당되어 파일(예: .csv 또는 .txt 목록) 또는 준수 센터에서 가져올 수 있는 목록에서 가져올 [수 있습니다.](create-a-keyword-dictionary.md) 조직 및 정책과 관련한 용어 또는 언어를 지원해야 하는 경우 사용자 지정 사전을 사용 합니다.

### <a name="classifiers"></a>분류자

교육 가능한 기본 제공 분류자 및 전역 분류자 검사는 조직의 모든 통신 채널에서 보내거나 받은 메시지를 검사하여 다양한 유형의 규정 준수 문제를 검사합니다. 분류자는 괴롭힘 방지 정책을 위반할 가능성이 큰 언어를 메시지에서 식별하기 위해 인공 지능과 키워드의 조합을 사용합니다. 기본 제공 분류기는 현재 여러 언어로 메시지 키워드 식별을 지원하고 있습니다.

- 중국어(간체)
- 영어
- 프랑스어
- 독일어
- 이탈리아어
- 일본어
- 포르투갈어
- 스페인어

커뮤니케이션 규정 준수 기본 제공 교육 가능 및 전역 분류자들은 다음 유형의 언어 및 콘텐츠에 대한 용어, 이미지 및 정서에 대한 통신을 검색합니다.

- **성인 이미지:** 본질적으로 명시적인 이미지를 검색합니다.
- **차별(미리 보기)**: 명시적 차별 언어를 검사하며, 다른 커뮤니티와 비교할 때 아프리카 아메리카/검은색 커뮤니티에 대한 차별 언어에 특히 민감합니다.
- **고리 이미지:** 폭력과 유해를 묘사하는 이미지를 검색합니다.
- **비언어:** 대부분의 사람들이 언성을 끄는 비음성 식을 검색합니다.
- **인종 이미지:** 본질적으로 성적으로 권장되지만 성인으로 생각되는 이미지보다 명시적이지 않은 콘텐츠를 포함하는 이미지를 검색합니다.
- **대상 괴롭혔습니다.** 경마, 색, 분장, 국가 원점과 관련하여 타기팅하는 공격적인 행동을 검사합니다.
- **위협:** 사람 또는 속성에 대해 폭력이나 물리적인 피해를 가하는 위협을 검사합니다.

*성인,* *인종* 및  고리 이미지 분류자는 .jpeg, .png, .gif 및 형식의 .bmp 검색합니다. 이미지 파일의 크기는 4MB보다 작아야 합니다. 이미지의 크기는 50x50픽셀보다 크고 이미지가 50킬로바이트(KB)보다 커야 평가를 받을 수 있습니다. 이미지 식별은 전자 메일 메시지 및 Exchange Online 채널 및 Microsoft Teams 지원됩니다.

교육 가능한 기본 제공 분류자 및 전역 분류자에서는 이러한 영역에서 용어 또는 이미지의 전체 목록을 제공하지 않습니다. 또한 언어 및 문화 표준은 지속적으로 변경되고 이러한 현실을 생각할 때 Microsoft는 재량에 따라 분류자 업데이트할 수 있는 권리가 있습니다. 분류자 조직에서 이러한 영역을 모니터링하는 데 도움이 될 수 있지만 분류자만이 이러한 언어 또는 이미지를 모니터링하거나 처리하기 위한 목적으로만 제공되지는 않습니다. Microsoft가 아닌 조직은 로컬 개인 정보 보호 및 기타 관련 법률 준수를 포함하여 이러한 영역에서 언어 및 이미지 모니터링, 검사 및 차단과 관련된 모든 결정에 대한 책임을 져야 합니다. Microsoft는 배포 및 사용 전에 법률 자문가와 상의하는 것이 좋습니다.

> [!NOTE]
> 분류기를 사용하는 정책은 단어 개수가 6개 이상인 메시지를 검사하고 평가합니다. 6개 미만의 단어를 포함하는 메시지는 분류기를 사용하여 정책에서 평가되지 않습니다. 부적절한 콘텐츠를 포함하는 더 짧은 메시지를 식별하고 조치를 취하려면 이러한 유형의 콘텐츠에 대한 통신 준수 정책 모니터링에 사용자 지정 키워드 사전을 포함하는 것이 좋습니다.

교육 가능한 분류자에 대한 자세한 Microsoft 365 학습 가능한 분류자 [시작하기를 참조하세요.](classifier-get-started-with.md)

### <a name="optical-character-recognition-ocr"></a>광학 문자 인식(OCR)

조직에서 부적절할 수 있는 이미지에서 인쇄되거나 필기한 텍스트를 검색하고 식별하도록 기본 제공 또는 사용자 지정 통신 준수 정책을 구성합니다. [이미지에서](/azure/cognitive-services/computer-vision/overview-ocr) 텍스트를 식별하기 위한 통합 Azure 인지 서비스 및 광학 검색 지원을 통해 분석가와 조사자는 주로 텍스트가 아닌 통신에서 부적절한 행동이 누락될 수 있는 경우를 감지하고 작업을 할 수 있습니다.

템플릿, 사용자 지정 정책의 새 정책에서 OCR(광학 문자 인식)을 사용하도록 설정하거나 기존 정책을 업데이트하여 포함된 이미지 및 첨부 파일 처리에 대한 지원을 확장할 수 있습니다. 정책 템플릿에서 만든 정책에서 사용하도록 설정하면 전자 메일 및 채팅 메시지에 포함된 이미지 또는 첨부된 이미지에 대해 자동 Microsoft Teams 지원됩니다. 문서 파일에 포함된 이미지의 경우 OCR 검색이 지원되지 않습니다. 사용자 지정 정책의 경우 정책에서 키워드, 기본 제공 분류자 또는 중요한 정보 유형과 연결된 하나 이상의 조건부 설정을 구성하여 OCR 검색을 선택해야 합니다.

다음 이미지 형식의 50 KB에서 4MB까지의 이미지를 검사하고 처리합니다.

- .jpg/.jpeg(공동 사진 전문가 그룹)
- .png(휴대용 네트워크 그래픽)
- .bmp(비트맵)
- .tiff(태그 이미지 파일 형식)
- .pdf(이동식 문서 형식)

> [!NOTE]
> 포함 및 첨부된 이미지에 대한 .pdf 추출은 현재 전자 메일 메시지에 한해 지원됩니다.

OCR을 사용하는 정책에 대해 보류 중인 경고를 검토할 때 식별되고 정책 조건과 일치하는 이미지는 연결된 경고의 하위 항목으로 표시됩니다. 원본 이미지를 보고 원본 메시지와 함께 컨텍스트에서 식별된 텍스트를 평가할 수 있습니다. 경고에서 검색된 이미지를 사용할 수 있는 데 최대 48시간이 걸릴 수 있습니다.

### <a name="conditional-settings"></a>조건부 설정
<a name="ConditionalSettings"> </a>

정책에 대해 선택한 조건은 조직의 전자 메일 및 타사 소스(예: Instant Bloomberg에서)의 통신에 적용됩니다.

다음 표에서는 각 조건에 대한 자세한 설명을 제공합니다.

|**조건**|**이 조건을 사용하는 방법**|
|:-----|:-----|
| **콘텐츠가 다음 분류자와 일치** | 분류자 중 어느 것이 메시지에 포함되거나 제외될 때 정책에 적용됩니다. 일부 분류자는 테넌트에 미리 정의되어 있으며 사용자 지정 분류자는 이 조건에 사용할 수 있도록 하기 전에 별도로 구성해야 합니다. 하나의 분류자만 정책에서 조건으로 정의할 수 있습니다. 분류자 구성에 대한 자세한 내용은 학습 가능한 분류자에 대한 자세한 정보(미리 [보기)를 참조하세요.](classifier-learn-about.md) |
| **콘텐츠에 다음 중요한 정보 유형이 포함되어 있습니다.** | 메시지에 중요한 정보 유형이 포함되거나 제외될 때 정책에 적용합니다. 일부 분류기는 테넌트에 미리 정의되어 있으며, 사용자 지정 분류자도 별도로 구성하거나 조건 할당 프로세스의 일부로 구성할 수 있습니다. 선택한 각 중요한 정보 유형은 별도로 적용되고 이러한 중요한 정보 유형 중 하나만 적용해야 정책이 메시지에 적용됩니다. 사용자 지정 중요한 정보 유형에 대한 자세한 내용은 중요한 정보 유형에 대한 자세한 [정보를 참조하세요.](sensitive-information-type-learn-about.md) |
| **다음 도메인에서 메시지를 수신합니다.**  <br><br> **이러한 도메인에서 메시지를 받지 못했습니다.** | 받은 메시지에 특정 도메인 또는 전자 메일 주소를 포함하거나 제외하려면 정책을 적용합니다. 각 도메인 또는 전자 메일 주소를 입력하고 여러 도메인 또는 전자 메일 주소를 콤보로 구분합니다. 입력한 각 도메인 또는 전자 메일 주소는 개별적으로 적용되고, 정책이 메시지에 적용하려면 도메인 또는 전자 메일 주소 하나만 적용해야 합니다. <br><br> 특정 도메인의 모든 전자 메일을 검색하지만 검토할 필요가 없는 메시지(뉴스레터, 알림 등)를 제외하려면 전자 메일  주소를 제외하는 이러한 도메인 조건(예: "newsletter@contoso.com")에서 메시지를 받지 못하도록 구성해야 합니다. |
| **메시지가 다음 도메인으로 전송됩니다.**  <br><br> **메시지가 이러한 도메인으로 전송되지 않습니다.** | 보낸 메시지에 특정 도메인 또는 전자 메일 주소를 포함하거나 제외하려면 정책을 적용합니다. 각 도메인 또는 전자 메일 주소를 입력하고 여러 도메인 또는 전자 메일 주소를 콤보로 구분합니다. 각 도메인 또는 전자 메일 주소는 개별적으로 적용되고 정책이 메시지에 적용하려면 도메인 또는 전자 메일 주소 하나만 적용해야 합니다. <br><br> 특정 도메인으로 전송된 모든 전자 메일을 검색하지만 검토할 필요가 없는 보낸 메시지를 제외하려면 다음 두 가지 조건을 구성해야 합니다. <br> - **메시지가** 도메인("contoso.com")을 정의하는 이러한 도메인 조건으로 전송됩니다. <br> - **전자 메일** 주소("subscriptions@contoso.com")를 제외하는 이러한 도메인 조건으로 메시지가 전송되지 않습니다. |
| **메시지가 다음 레이블로 분류됩니다.**  <br><br> **메시지가 이러한 레이블로 분류되지 않습니다.** | 메시지에 특정 보존 레이블이 포함되거나 제외될 때 정책을 적용합니다. 보존 레이블은 별도로 구성해야 합니다. 이 조건의 일부로 구성된 레이블이 선택됩니다. 선택한 각 레이블은 별도로 적용됩니다(메시지에 적용할 정책에는 이러한 레이블 중 하나만 적용해야 합니다). 보존 레이블에 대한 자세한 내용은 보존 정책 및 보존 레이블에 대해 자세히를 [참조하세요.](retention.md)|
| **다음 단어가 포함된 메시지**  <br><br> **메시지에 다음 단어가 없음** | 메시지에 특정 단어나 구가 포함되거나 제외될 때 정책을 적용하기 위해 각 단어를 콤보로 구분하여 입력합니다. 두 단어 이상의 구의 경우 구 주위에 인용 부호를 사용 합니다. 입력하는 각 단어 또는 구는 별도로 적용됩니다(메시지에 적용하려면 한 단어만 적용해야 합니다). 단어나 구를 입력하는 데 대한 자세한 내용은 다음 섹션 전자 메일 또는 첨부 파일에 단어 및 구 [일치를 참조하세요.](communication-compliance-policies.md#Matchwords)|
| **Attachment에 다음 단어가 포함되어 있습니다.**  <br><br> **Attachment에 다음 단어가 포함되어 없음** | 특정 단어나 구가 메시지 첨부 파일(예: Word 문서)에 포함되거나 제외될 때 정책을 적용하기 위해 각 단어를 각 단어를 0으로 구분하여 입력합니다. 두 단어 이상의 구의 경우 구 주위에 인용 부호를 사용 합니다. 입력하는 각 단어 또는 구는 별도로 적용됩니다(첨부 파일에 적용하려면 한 단어만 적용해야 합니다). 단어나 구를 입력하는 데 대한 자세한 내용은 다음 섹션 전자 메일 또는 첨부 파일에 단어 및 구 [일치를 참조하세요.](communication-compliance-policies.md#Matchwords)|
| **Attachment is any of these file types**  <br><br> **첨부 파일이 이러한 파일 형식이 없음** | 특정 유형의 첨부 파일을 포함하거나 제외하는 통신을 감독하기 위해 파일 확장명(예: .exe 또는 .pdf)을 입력합니다. 여러 파일 확장명을 포함하거나 제외하려는 경우 이러한 확장명을 별도의 줄에 입력합니다. 정책을 적용하려면 하나의 첨부 파일 확장명만 일치해야 합니다.|
| **메시지 크기가 보다 크기**  <br><br> **메시지 크기가 작지 않습니다.** | 특정 크기에 따라 메시지를 검토하기 위해 다음 조건을 사용하여 메시지의 검토 대상이 되기 전의 최대 또는 최소 크기를 지정합니다. 예를 들어 메시지  크기가 \> **1.0MB보다** 크면 1.01MB 이상인 모든 메시지를 검토할 수 있습니다. 이 조건에 대해바이트, 킬로바이트, 메가바이트 또는 기가바이트를 선택할 수 있습니다.|
| **첨부 파일이 보다 크기**  <br><br> **첨부 파일이 작지 않습니다.** | 첨부 파일 크기에 따라 메시지를 검토하기 위해 첨부 파일이 메시지 및 첨부 파일을 검토하기 전까지의 최대 또는 최소 크기를 지정합니다. 예를 들어 **Attachment가** \> **2.0MB보다** 크면 첨부 파일이 2.01MB 이상인 모든 메시지는 검토할 수 있습니다. 이 조건에 대해바이트, 킬로바이트, 메가바이트 또는 기가바이트를 선택할 수 있습니다.|

#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>전자 메일 또는 첨부 파일에 단어 및 구 일치
<a name="Matchwords"> </a>

입력하는 각 단어와 콤보로 구분하는 단어는 개별적으로 적용됩니다(정책 조건이 전자 메일 또는 첨부 파일에 적용하려면 한 단어만 적용되어야 합니다). 예를 들어 **다음** 단어가 메시지에 포함된 조건과 키워드 "banker", "confidential" 및 "insider trading"를 각 MA(은행원, 기밀, "내부자 거래")로 구분하여 사용해 보겠습니다. 이 정책은 "은행원", "기밀" 또는 "내부자 거래" 구를 포함하는 모든 메시지에 적용됩니다. 이 정책 조건을 적용하려면 이러한 단어 또는 구 중 하나만 발생해야 합니다. 메시지 또는 첨부 파일에 있는 단어는 입력한 단어와 정확히 일치해야 합니다.

> [!IMPORTANT]
>
> 사용자 지정 사전 파일을 가져올 때 각 단어나 구는 캐리지 리턴과 별도의 줄로 구분해야 합니다. 예제:
>
> *banker* <br>
> *confidential* <br>
> *내부자 거래*

전자 메일 메시지와 첨부 파일에서 동일한 키워드를 [](create-a-keyword-dictionary.md) 모두 검색하려면 메시지에서 검색할 용어에 대한 사용자 지정 키워드 사전을 만드면 됩니다. 이 정책 구성은 전자 메일 메시지 또는 전자 메일 첨부 파일에 나타나는 **정의된** 키워드를 식별합니다. 표준 조건부 정책 설정(*메시지에는* 다음 단어가 포함되어 있으며 *Attachment에는* 다음 단어 중 하나만 포함)을  사용하여 메시지의 용어를 식별하고 첨부 파일에 용어를 포함하려면 메시지와 첨부 파일에 용어를 모두 포함해야 합니다.

#### <a name="enter-multiple-conditions"></a>여러 조건 입력

여러 조건을 입력하면 Microsoft 365 모든 조건을 함께 사용하여 통신 항목에 통신 준수 정책을 적용할 때를 결정할 수 있습니다. 여러 조건을 설정할 때 예외를 입력하지 않는 한 정책이 적용될 모든 조건을 충족해야 합니다. 예를 들어 메시지에 "trade"라는 단어가 포함되어 있으며 2MB보다 큰 경우 적용되는 정책이 필요합니다. 그러나 메시지에 "Approved by Contoso financial"의 단어도 포함된 경우 정책을 적용하면 안 됩니다. 이 예에서 세 조건은 다음과 같이 정의됩니다.

- **메시지에 다음 단어 중 하나와** 키워드 "trade"가 포함되어 있습니다.
- **메시지 크기가 보다** 크며 값 2MB
- **메시지에는**"Contoso 재무 팀에서 승인했습니다."라는 키워드가 포함된 단어가 없습니다.

### <a name="review-percentage"></a>검토 백분율

검토할 콘텐츠의 양을 줄이면 통신 준수 정책이 적용하는 모든 통신의 백분율을 지정할 수 있습니다. 선택된 정책 조건에 부합하는 콘텐츠의 총 백분율로 무작위 샘플이 실시간으로 선택됩니다. 검토자가 모든 항목을 검토하게 하려면, 커뮤니케이션 규정 준수 정책에서 **100%** 를 구성합니다.

## <a name="alert-policies"></a>알림 정책

정책을 구성하면 해당 경고 정책이 자동으로 만들어지며 정책에 정의된 조건과 일치하는 메시지에 대해 경고가 생성됩니다. 활동 표시기에서 알림을 받기 위한 정책을 만들고 나면 최대 24시간이 걸릴 수 있습니다. 기본적으로 모든 정책 일치 경고 트리거에는 연결된 경고 정책에서 심각도 수준 보통이 할당됩니다. 연결된 경고 정책에서 집계 트리거 임계값 수준이 충족되면 통신 준수 정책에 대한 알림이 생성됩니다. 단일 전자 메일 알림은 정책 조건과 일치하는 개별 메시지 수에 관계없이 모든 경고에 대해 24시간마다 한 번 전송됩니다. 예를 들어 Contoso는 부적절한 콘텐츠 정책을 사용하도록 설정하고 1월 1일 동안 경고를 6개 생성한 100개 정책 일치가 있습니다. 6개 경고에 대한 단일 전자 메일 알림이 1월 1일 말에 전송됩니다.

통신 준수 정책의 경우 기본적으로 다음과 같은 경고 정책 값이 구성됩니다.

|**경고 정책 트리거**|**기본값**.|
|:-----|:-----|
| 집계 | 단순 집계 |
| 임계값 | 기본값: 4개 활동 <br> 최소: 3개 활동 <br> 최대: 2,147,483,647개 활동 |
| 창 | 기본값: 60분 <br> 최소: 60분 <br> 최대값: 10,000분 |

> [!NOTE]
> 활동에 대한 경고 정책 임계값 트리거 설정은 통신 준수 정책에 대해 최소값 3 이상을 지원합니다.

작업 수, 활동 기간 및 알림 정책 페이지의 경고 정책에서 특정 사용자에 대한  트리거에 대한 기본 설정을 변경할 수 Microsoft 365 규정 준수 센터.

### <a name="change-the-severity-level-for-an-alert-policy"></a>경고 정책의 심각도 수준 변경

특정 통신 준수 정책에 대한 경고 정책에 할당된 심각도 수준을 변경하고자 하는 경우 다음 단계를 완료합니다.

1. 조직에서 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com) 계정의 자격 증명을 사용하여 로그인합니다Microsoft 365.

2. In the Microsoft 365 규정 준수 센터, go to **Policies**.

3. 정책 **Office 365 경고를** 선택하여  경고 정책 **페이지를 열** 수 있습니다.

4. 업데이트할 통신 준수 정책의 확인란을 선택한 다음 정책 편집 **을 선택합니다.**

5. 설명 **탭에서** 심각도  드롭다운을 선택하여 정책 경고 수준을 구성합니다.

6. **저장을** 선택하여 새 심각도 수준을 정책에 적용합니다.

7. 닫기 **를** 선택하여 경고 정책 세부 정보 페이지를 종료합니다.
