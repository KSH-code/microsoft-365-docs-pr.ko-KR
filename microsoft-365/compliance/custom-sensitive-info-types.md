---
title: DLP에 대한 사용자 지정 중요한 정보 유형
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 'DLP(데이터 손실 방지)에 대한 사용자 지정 중요한 정보 유형(예: 기본 패턴, 문자 근접성, 신뢰 수준)의 개요를 확인합니다.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817967"
---
# <a name="custom-sensitive-information-types"></a>사용자 지정 중요한 정보 유형

Microsoft 365에는 [데이터 손실 방지](data-loss-prevention-policies.md)(DLP) 또는 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)와 같이 조직에서 사용하도록 기본으로 제공되는 많은 중요한 정보 유형이 포함되어 있습니다. 기본 제공되는 중요한 정보 유형은 정규 표현식(정규식) 또는 함수로 정의된 패턴을 기반으로 신용 카드 번호, 은행 계좌 번호, 여권 번호 등을 식별하고 보호하는 데 도움이 될 수 있습니다. 자세한 내용은 [중요한 정보 유형이 찾는 항목](what-the-sensitive-information-types-look-for.md)을 참조하십시오.

그렇지만 다른 유형의 중요한 정보, 예를 들어, 조직 고유의 형식을 사용하는 직원 ID 또는 프로젝트 번호를 식별하고 보호해야 할 경우 어떻게 하나요? 이를 위해 사용자 지정 중요한 정보 유형을 만들 수 있습니다.

다음은 사용자 지정 중요한 정보 유형의 기본 구성 요소입니다.

- **기본 패턴**: 직원 ID 번호, 프로젝트 번호 등으로, 일반적으로 정규식(RegEx)으로 식별되지만, 해당 패턴이 키워드 목록일 수도 있습니다.

- **Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.

- **Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:

    ![증거 및 근접 범위 다이어그램](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.

  When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:

    ![인스턴스 개수 및 일치 정확도 옵션](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>사용자 지정 중요한 정보 유형 만들기

보안 및 준수 센터에서 사용자 지정 중요한 정보 유형을 만들려면 몇 가지 옵션 중에서 선택할 수 있습니다.

- **EDM 사용**(신규!) EDM(Exact Data Match) 기반 분류를 사용하여 사용자 정의 중요한 정보 유형을 설정할 수 있습니다. 이 방법을 사용하면 주기적으로 새로 고칠 수 있는 보안 데이터베이스를 사용하여 동적인 중요한 정보 유형을 만들 수 있습니다. [분류에 기반한 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)를 참조하십시오.

- **PowerShell을 사용** PowerShell을 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니다. 이 방법은 UI를 사용하는 것보다 복잡하지만 더 다양한 구성 옵션이 있습니다. [보안 및 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type-in-scc-powershell.md)를 참조하십시오.

- **UI 사용** 보안 및 준수 센터 UI를 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니나. 이 방법을 사용하면 정규식, 키워드 및 키워드 사전을 사용할 수 있습니다. 자세한 내용은 [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)을 참조하십시오.



