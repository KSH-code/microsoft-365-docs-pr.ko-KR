---
title: DLP 정책 조건, 예외 및 작업 (미리 보기)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: dlp 정책 조건 및 예외에 대해 자세히 알아보기
ms.openlocfilehash: a371c564cc314c457e1d9afe667115c244e0185d
ms.sourcegitcommit: f941495e9257a0013b4a6a099b66c649e24ce8a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993346"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>DLP 정책 조건, 예외 및 작업 (미리 보기)

DLP 정책의 조건 및 예외로 정책이 적용 되는 중요 한 항목을 식별 합니다. 작업은 예외 발생 조건의 결과로 발생 하는 작업을 정의 합니다.

- 포함할 내용 정의 조건
- 예외 제외할 항목을 정의 합니다.
- 작업 조건 또는 예외가 충족 되는 결과를 정의 합니다.
 
대부분의 조건 및 예외에는 하나 이상의 값을 지 원하는 속성이 하나 있습니다. 예를 들어 Exchange 전자 메일에 DLP 정책을 적용 하는 경우 **보낸 사람** is 조건은 메시지를 보낸 사람을 요구 합니다. Some conditions have two properties. 예를 들어 **메시지 헤더에 다음 단어 중 하나라도 포함 되어** 있으면 메시지 헤더 필드를 지정 하는 속성 한 개와 헤더 필드에서 찾을 텍스트를 지정 하는 두 번째 속성을 사용 해야 합니다. 일부 조건 또는 예외에 속성이 없는 경우 예를 들어 **첨부 파일이 암호로 보호** 된 경우에는 암호로 보호 된 메시지의 첨부 파일만 찾습니다.

작업에는 일반적으로 추가 속성이 필요 합니다. 예를 들어 DLP 정책 규칙이 메시지를 리디렉션하는 경우 메시지를 리디렉션할 위치를 지정 해야 합니다. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>DLP 정책에 대 한 조건 및 예외 사항

다음 섹션의 표에는 DLP에서 사용할 수 있는 조건 및 예외에 대 한 설명이 나와 있습니다.

- [보낸 사람](#senders)
- [받는 사람](#recipients)
- [메시지 제목 또는 본문](#message-subject-or-body)
- [첨부 파일](#attachments)
- [메시지 헤더](#message-headers)
- [메시지 속성](#message-properties)

### <a name="senders"></a>보낸 사람


|**DLP의 조건 또는 예외**  |**Microsoft 365 PowerShell의 조건/예외 매개 변수** |**속성 형식**  |**설명이**|
|---------|---------|---------|---------|
|보낸 사람이 |조건: *보낸 사람* <br/> 예외: *ExceptIfFrom*      |Addresses |     조직의 지정 된 사서함, 메일 사용자, 메일 연락처 또는 Microsoft 365 그룹으로 전송 되는 메시지입니다.|
|보낸 사람 IP 주소는     |조건: *SenderIPRanges*<br/> 예외: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | 보낸 사람의 IP 주소가 지정 된 IP 주소와 일치 하거나 지정 된 IP 주소 범위 내에 있는 메시지입니다.       |
|보낸 사람 주소에 단어 포함   | 조건: *FromAddressContainsWords* <br/> 예외: *ExceptIfFromAddressContainsWords*        |   말해      |   보낸 사람의 전자 메일 주소에 지정 된 단어가 포함 된 메시지입니다.|
| 보낸 사람 주소가 패턴과 일치    | 조건: *FromAddressMatchesPatterns* <br/> 예외: *ExceptFromAddressMatchesPatterns*       |      방법   |  보낸 사람의 전자 메일 주소에 지정 된 정규식과 일치 하는 텍스트 패턴이 포함 된 메시지입니다.  |
|보낸 사람 도메인  |  조건: *SenderDomainIs* <br/> 예외: *ExceptIfSenderDomainIs*       |도메인         |     보낸 사람의 전자 메일 주소 도메인이 지정 된 값과 일치 하는 메시지 지정한 도메인 (예: 도메인의 하위 도메인)을 *포함* 하는 보낸 사람 도메인을 찾아야 하는 경우에는 **보낸 사람 주소 일치** ( *FromAddressMatchesPatterns* ) 조건을 사용 하 고 ' \. domain \. com $ ' 구문을 사용 하 여 도메인을 지정 합니다.    |

### <a name="recipients"></a>받는 사람

|**DLP의 조건 또는 예외**| **Microsoft 365 PowerShell의 조건/예외 매개 변수** |    **속성 형식** | **설명이**|
|---------|---------|---------|---------|
|받는 사람은|  조건: *SentTo* <br/> 예외: *ExceptIfSentTo* | Addresses | 받는 사람 중 한 사람이 조직의 지정 된 사서함, 메일 사용자 또는 메일 연락처 인 메시지입니다. 받는 사람은 메시지 **의 받는 사람,** **참조** 또는 **숨은 참조** 필드에 있을 수 있습니다.|
|받는 사람 도메인은|   조건: *RecipientDomainIs* <br/> 예외: *ExceptIfRecipientDomainIs* |   도메인 |    보낸 사람의 전자 메일 주소 도메인이 지정 된 값과 일치 하는 메시지|
|받는 사람 주소에 단어 포함|  조건: *RecipientAddressContainsWords* <br/> 예외: *ExceptIfRecipientAddressContainsWords*|    말해|  받는 사람의 전자 메일 주소에 지정 된 단어가 포함 된 메시지입니다. <br/>**참고** : 이 조건은 받는 사람 프록시 주소로 보낸 메시지는 고려하지 않습니다. 받는 사람의 기본 전자 메일 주소로 보낸 메시지만 일치시킵니다.|
|받는 사람 주소가 패턴과 일치| 조건: *RecipientAddressMatchesPatterns* <br/> 예외: *ExceptIfRecipientAddressMatchesPatterns*|   방법    |받는 사람의 전자 메일 주소에 지정 된 정규식과 일치 하는 텍스트 패턴이 포함 된 메시지입니다. <br/> **참고** : 이 조건은 받는 사람 프록시 주소로 보낸 메시지는 고려하지 않습니다. 받는 사람의 기본 전자 메일 주소로 보낸 메시지만 일치시킵니다.|
|다음 구성원에 게 보냄| 조건: *SentToMemberOf* <br/> 예외: *ExceptIfSentToMemberOf*|  Addresses|  지정 된 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹의 구성원 인 받는 사람이 포함 된 메시지입니다. 그룹은 메시지의 **받는** **사람, 참조** 또는 **숨은 참조** 필드에 있을 수 있습니다.|

### <a name="message-subject-or-body"></a>메시지 제목 또는 본문

|**DLP의 조건 또는 예외** | **Microsoft 365 PowerShell의 조건/예외 매개 변수** |**속성 형식**| **설명이**|
|---------|---------|---------|---------|
|제목에 단어 또는 구가 포함 된 경우| 조건: *SubjectContainsWords* <br/> 예외: *ExceptIf SubjectContainsWords*| 말해   |제목 필드에 지정 된 단어가 포함 된 메시지입니다.|
|제목 일치 패턴|조건: *SubjectMatchesPatterns* <br/> 예외: *ExceptIf SubjectMatchesPatterns*|방법   |제목 필드에 지정 된 정규식과 일치 하는 텍스트 패턴이 포함 된 메시지입니다.|
|콘텐츠에 포함 된 내용|  조건: *ContentContainsSensitiveInformation* <br/> 예외 *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  DLP (데이터 손실 방지) 정책에 정의 된 중요 한 정보가 포함 된 메시지 또는 문서|


### <a name="attachments"></a>첨부 파일

|**DLP의 조건 또는 예외**| **Microsoft 365 PowerShell의 조건/예외 매개 변수**| **속성 형식**   |**설명이**|
|---------|---------|---------|---------|
|첨부 파일이 암호로 보호됨|조건: *DocumentIsPasswordProtected* <br/> 예외: *ExceptIfDocumentIsPasswordProtected*|없음| 첨부 파일이 암호로 보호 되어 있으므로 검색할 수 없는 메시지입니다. 암호 검색은 Office 문서 및 .zip 파일에 대해서만 작동 합니다.|
|첨부 파일 확장명|조건: *ContentExtensionMatchesWords* <br/> 예외: *ExceptIfContentExtensionMatchesWords*|  말해   |첨부 파일의 확장명이 지정 된 단어와 일치 하는 메시지|
|모든 전자 메일 첨부 파일의 콘텐츠를 검색할 수 없음|조건: *DocumentIsUnsupported* <br/>예외: *ExceptIf DocumentIsUnsupported*|   해당 없음|    Exchange Online에서 첨부 파일이 기본적으로 인식 되지 않는 메시지|
|모든 전자 메일 첨부 파일의 콘텐츠가 검색을 완료 하지 못함|   조건: *ProcessingLimitExceeded* <br/> 예외: *ExceptIfProcessingLimitExceeded*|    해당 없음 |규칙 엔진이 첨부 파일 검사를 완료 하지 못한 메시지입니다. 이 조건을 사용 하 여 콘텐츠를 완벽 하 게 검색할 수 없는 메시지를 식별 하 고 처리 하기 위해 함께 작동 하는 규칙을 만들 수 있습니다.|
|문서 이름에 단어 포함|condition: *Documentnamematcheswords* <br/> 예외: *ExceptIfDocumentNameMatchesWords* |말해  |첨부 파일 이름이 지정 된 단어와 일치 하는 메시지|
|문서 이름이 패턴과 일치 함|조건: *DocumentNameMatchesPatterns* <br/> 예외: *ExceptIfDocumentNameMatchesPatterns*|    방법    |첨부 파일 이름에 지정 된 정규식과 일치 하는 텍스트 패턴이 있는 메시지입니다.|
|문서 속성은|조건: *ContentPropertyContainsWords* <br/> 예외: *ExceptIfContentPropertyContainsWords* |말해| 첨부 파일 확장명이 지정 된 단어와 일치 하는 메시지 또는 문서|
|문서 크기가 다음 보다 크거나 같습니다.| 조건: *Documentsizeover* <br/> 예외: *ExceptIfDocumentSizeOver*|    크기    |지정 된 값 보다 크거나 같은 첨부 파일이 있는 메시지|

### <a name="message-headers"></a>메시지 헤더

|**DLP의 조건 또는 예외**| **Microsoft 365 PowerShell의 조건/예외 매개 변수**| **속성 형식**|  **설명이**|
|---------|---------|---------|---------|
|머리글에 단어 또는 구 포함|조건: *HeaderContainsWords* <br/> 예외: *ExceptIfHeaderContainsWords*|  해시 테이블  |지정한 머리글 필드를 포함 하는 메시지와 해당 헤더 필드의 값에 지정한 단어가 포함 되어 있습니다.|
|헤더가 일치 하는 패턴|   조건: *HeaderMatchesPatterns* <br/> 예외: *ExceptIfHeaderMatchesPatterns*|    해시 테이블  |지정한 헤더 필드를 포함 하는 메시지와 해당 헤더 필드의 값에 지정한 정규식이 포함 되어 있는 경우|

### <a name="message-properties"></a>메시지 속성

|**DLP의 조건 또는 예외**| **Microsoft 365 PowerShell의 조건/예외 매개 변수**| **속성 형식**   |**설명이**|
|---------|---------|---------|---------|
|메시지 크기 초과|조건: *MessageSizeOver* <br/> 예외: *ExceptIfMessageSizeOver*| 크기    |총 크기 (메시지 + 첨부 파일)가 지정 된 값 보다 크거나 같은 메시지입니다. <br/>**참고** : 사서함에 대 한 메시지 크기 제한은 메일 흐름 규칙 보다 먼저 평가 됩니다. 이 조건에 해당 하는 규칙을 사용 하 여 메시지에 대 한 작업을 수행할 수 있으려면 사서함에 대해 너무 큰 메시지를 거부 합니다.|

## <a name="actions-for-dlp-policies"></a>DLP 정책에 대 한 작업

이 표에서는 DLP에서 사용할 수 있는 Exchange Online 메일 흐름 규칙 작업에 대해 설명 합니다.


|**DLP의 작업**|**Microsoft 365 PowerShell의 작업 매개 변수**|**속성 형식**|**설명이**|
|---------|---------|---------|---------|
|머리글 설정|SetHeader|첫 번째 속성: *헤더 이름* </br> 두 번째 속성: *헤더 값*|SetHeader 매개 변수는 메시지 헤더에 헤더 필드 및 값을 추가 하거나 수정 하는 DLP 규칙에 대 한 작업을 지정 합니다. 이 매개 변수는 "인원 Ername: HeaderValue" 구문을 사용 합니다. 여러 헤더 이름 및 값 쌍을 쉼표로 구분 하 여 지정할 수 있습니다.|
|헤더 제거| RemoveHeader| 첫 번째 속성: *MessageHeaderField*</br> 두 번째 속성: *String*|  RemoveHeader 매개 변수는 메시지 헤더에서 헤더 필드를 제거 하는 DLP 규칙에 대 한 작업을 지정 합니다. 이 매개 변수는 "인원 Ername" 또는 "인원 Ername: HeaderValue" 구문을 사용 합니다. 여러 헤더 이름 또는 헤더 이름 및 값 쌍을 쉼표로 구분 하 여 지정할 수 있습니다.|
|메시지를 특정 사용자에 게 리디렉션|*RedirectMessageTo*|Addresses| 메시지를 지정 된 받는 사람에 게 리디렉션합니다. 원래 받는 사람에게 메시지가 배달되지 않으며, 보낸 사람이나 원래 받는 사람에게 알림이 전송되지 않습니다.|
|보낸 사람의 관리자에 게 승인을 위해 메시지 전달| 보통|첫 번째 속성: *ModerateMessageByManager*</br> 두 번째 속성: *Boolean*|중간 매개 변수는 중재자에 게 전자 메일 메시지를 보내는 DLP 규칙에 대 한 작업을 지정 합니다. 이 매개 변수는 @ {ModerateMessageByManager = <$true $false> 구문을 사용 합니다. \||
|특정 승인자에 게 승인을 위해 메시지 전달| 보통|첫 번째 속성: *ModerateMessageByUser*</br>두 번째 속성: *주소*|중간 매개 변수는 중재자에 게 전자 메일 메시지를 보내는 DLP 규칙에 대 한 작업을 지정 합니다. 이 매개 변수는 @ {ModerateMessageByUser = @ ("emailaddress1", "emailaddress2",... "emailaddressN")} 구문을 사용 합니다.|
|받는 사람 추가|AddRecipients|첫 번째 속성: *Field*</br>두 번째 속성: *주소*| 메시지의 받는 사람/참조/숨은 참조 필드에 수신자를 한 명 이상 추가 합니다. 이 매개 변수는 @ {<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"} 구문을 사용 합니다.|
|보낸 사람의 관리자를 받는 사람으로 추가|AddRecipients | 첫 번째 속성: *Ad모든 Manageraction*</br>두 번째 속성: *필드* | 보낸 사람의 관리자를 지정 된 받는 사람, 참조, 숨은 참조 등의 메시지에 추가 하거나 보낸 사람 또는 받는 사람에 게 알리지 않고 보낸 사람의 관리자에 게 메시지를 리디렉션합니다. 이 작업은 보낸 사람의 관리자 특성이 Active Directory에 정의 된 경우에만 작동 합니다. 이 매개 변수는 @ {AddManagerAsRecipientType = "<\| 참조 \| 숨은 참조>"} 구문을 사용 합니다.|

