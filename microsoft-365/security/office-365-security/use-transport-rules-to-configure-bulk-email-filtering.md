---
title: 메일 흐름 규칙을 사용하여 대량 전자 메일 필터링
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 관리자는 메일 흐름 규칙(전송 규칙)을 사용하여 EOP(Exchange Online Protection)에서 대량 메일(회색 메일)을 식별하고 필터링하는 방법을 배를 나을 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfe841d3e80efc50d6ffbc702faefa1c9a971b13
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826756"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>메일 흐름 규칙을 사용하여 EOP에서 대량 전자 메일 필터링

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용하여 인바운드 메시지에서 스팸 및 대량 메일(회색 메일이라고도 함)을 검사합니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

대량 메일을 필터링하는 다른 옵션을 제공하려면 메일 흐름 규칙(전송 규칙이라고도 함)을 사용하여 대량 메일에서 자주 발견되는 텍스트 패턴이나 구를 검색하고 해당 메시지를 스팸으로 표시합니다. 대량 메일에 대한 자세한 내용은 정크 메일과 대량 전자 메일의 [차이점 및](what-s-the-difference-between-junk-email-and-bulk-email.md) [EOP의 BCL(대량 일반 수준) 간의 차이점을 참조하세요.](bulk-complaint-level-values.md)

이 항목에서는 EAC(Exchange 관리 센터) 및 PowerShell(Exchange Online 사서함을 포함한 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 이러한 메일 흐름 규칙을 만드는 방법에 대해 설명합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 이러한 절차를 수행하려면 먼저 사용 권한을 할당만 해야 합니다.

  - Exchange Online에서 Exchange Online의 기능 사용 권한에서 "메일 [흐름" 항목을 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)
  
  - 독립 실행형 EOP에는 기본적으로 OrganizationManagement, ComplianceManagement 및 RecordsManagement 역할에 할당된 전송 규칙 역할이 필요합니다. 자세한 내용은 독립 [실행형 EOP의 사용 권한을 참조하고](feature-permissions-in-eop.md) [EAC를 사용하여 역할 그룹의 구성원 목록을 수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Exchange Online에서 EAC를 열려면 Exchange Online의 [Exchange 관리 센터를 참조하세요.](https://docs.microsoft.com/Exchange/exchange-admin-center) 독립 실행형 EOP에서 EAC를 열려면 Exchange [관리 센터를 통해 독립 실행형 EOP를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대한 자세한 내용은 다음 항목을 참조하십시오.

  - [Exchange Online의 메일 흐름 규칙(전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online의 메일 흐름 규칙 동작](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 예제에서 대량 메일을 식별하는 데 사용되는 단어 및 텍스트 패턴 목록은 아주 산출하지 않습니다. 필요에 따라 항목을 추가 및 제거할 수 있습니다. 그러나 이 목록을 통해 시작하는 방법이 있습니다.

- ASCII 텍스트의 SMTP 서버 간에 바이너리 메시지를 전송하는 데 사용되는 MIME 콘텐츠 전송 인코딩 메서드에서 메시지가 디코딩된 *후* 메시지의 제목이나 다른 머리글 필드에 있는 단어 또는 텍스트 패턴이 검색됩니다. 조건이나 예외를 사용하여 메시지의 제목이나 다른 머리글 필드에 있는 원시(일반적으로, Base64) 인코딩된 값을 검색할 수 없습니다.

- 다음 절차에서는 전체 조직에 대한 대량 메시지를 스팸으로 표시합니다. 그러나 이러한 규칙을 다른 조건을 추가하여 이러한 규칙을 특정 받는 사람에게만 적용할 수도 있습니다. 그러면 일부 사용자는 최고 수준의 대상 사용자에 대해 적극적인 필터링을 사용할 수 있고 나머지 사용자(주로 등록한 대량 전자 메일을 받는 사용자)는 영향을 받지 않도록 할 수 있습니다.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>EAC를 사용하여 대량 전자 메일을 필터링하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.

2. 아이콘 **추가를** ![ 클릭한 다음 새 규칙 ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**

3. ** 새** 규칙 페이지에서 다음 설정을 구성합니다.

   - **이름:** 규칙을 설명하는 고유한 이름을 입력합니다.

   - 기타 **옵션을 클릭합니다.**

   - **다음의 경우 이 규칙**을 적용하십시오. 정규식(RegEx) 또는 단어나 구를 사용하여 메시지의 콘텐츠를 찾을 수 있도록 다음 설정 중 하나를 구성합니다.

     - **제목 또는 본문** \> **제목 또는 본문이 다음 텍스트 패턴과 일치합니다.** 표시되는 **단어 또는** 구 지정 대화 상자에서 **Add** 다음 값 중 하나를 입력하고, 아이콘 추가를 클릭한 후, 모든 값을 ![ ](../../media/ITPro-EAC-AddIcon.png) 입력할 때까지 반복합니다.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      항목을 편집하려면 항목을 선택한 후 편집 **아이콘을** ![ 클릭합니다. ](../../media/ITPro-EAC-EditIcon.png) 항목을 제거하려면 항목을 선택한 다음 제거 아이콘 **제거를** ![ 클릭합니다. ](../../media/ITPro-EAC-DeleteIcon.png)

       작업을 마친 후 **확인**을 클릭합니다.

     - **제목 또는 본문** \> **제목 또는 본문에 다음 단어 가 포함되어**있습니다. 표시되는 단어 **또는** 구 지정 대화 상자에서 **Add** 다음 값 중 하나를 입력하고, ![ 아이콘 추가를 클릭한 후, 모든 ](../../media/ITPro-EAC-AddIcon.png) 값을 입력할 때까지 반복합니다.

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      항목을 편집하려면 항목을 선택한 후 편집 **아이콘을** ![ 클릭합니다. ](../../media/ITPro-EAC-EditIcon.png) 항목을 제거하려면 항목을 선택한 다음 제거 아이콘 **제거를** ![ 클릭합니다. ](../../media/ITPro-EAC-DeleteIcon.png)

       작업을 마친 후 **확인**을 클릭합니다.

   - **다음 단계를** **수행합니다. 메시지** \> **속성을 선택하면 SCL(스팸 지수)이 설정되었습니다.** **나타나는 SCL** 지정 대화 상자에서 다음 설정 중 하나를 구성합니다.

     - 메시지를 스팸으로 **표시하려면** **6을 선택합니다.** 스팸 방지 정책에서 스팸 필터링 **결과에** 대해 구성한 작업은 메시지에 적용됩니다(기본값은 **메시지를 정크 메일 폴더로 이동).**

     - 메시지를 높은 **신뢰도의 스팸으로 표시하려면 9를** **선택합니다.** 스팸 방지 정책에서 높은 스팸 필터링 **결과에** 대해 구성한 작업은 메시지에 적용됩니다(기본값은 **메시지를 정크 메일 폴더로 이동).**

    SCL 값에 대한 자세한 내용은 [EOP에서 SCL(스팸 지수)를 참조하세요.](spam-confidence-levels.md)

   작업을 마치면 Save를 **클릭합니다.**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell을 사용하여 대량 전자 메일을 필터링하는 메일 흐름 규칙 만들기

다음 구문을 사용하여 메일 흐름 규칙(정규식 및 단어)을 하나 또는 모두 만듭니다.

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

이 예에서는 항목의 이전 것과 같은 정규식 목록을 사용하여 스팸으로 설정하는 "대량 전자 메일 필터링 - RegEx"라는 새 규칙을 **만듭니다.**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

다음은 항목의 앞부분에 있는 단어와 동일한 목록을 사용하여 메시지를 높은 지수 인값으로 설정하는 "대량 전자 메일 필터링 - Words"라는 새 **규칙을 만드는 예제입니다.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

대량 전자 메일을 필터링하도록 메일 흐름 규칙을 구성되었는지 확인하려면 다음 단계를 수행합니다.

- EAC에서 메일 흐름 **Mail flow** 규칙으로 \> **이동하여 규칙** \> 편집 \> 아이콘을 선택한 **다음** ![ ](../../media/ITPro-EAC-EditIcon.png) 설정을 확인합니다.

- PowerShell에서 \<Rule Name\> 규칙의 이름으로 바꾸고 다음 명령을 실행하여 설정을 확인합니다.

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 외부 계정에서 구 또는 텍스트 패턴 중 하나를 포함하는 영향을 받는 받는 사람에게 테스트 메시지를 보내 고 결과를 확인합니다.
