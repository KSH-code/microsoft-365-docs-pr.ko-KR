---
title: 조직 차원의 서명 및 부인 만들기
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 조직을 들어가거나 탈퇴 하는 모든 전자 메일 메시지에 전자 메일 서명, 법적 고 지 사항 또는 공개 설명을 추가 하는 방법을 알아봅니다.
ms.openlocfilehash: d7e19c6e3f425f95429aefd769d2b8992fde141e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779884"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>조직 차원의 서명 및 부인 만들기

 You can add an email signature, legal disclaimer, or disclosure statement to the email messages that enter or leave your organization. You can set it up to apply to all incoming and outgoing messages as shown below. Or you can apply it to certain messages like those containing specific words or text patterns.

 회사 차원의 전자 메일 서명을 만드는 방법에 대 한 간단한 비디오를 시청 하세요. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.

## <a name="create-a-signature-that-applies-to-all-messages"></a>모든 메시지에 적용되는 서명 만들기

> [!TIP]
> 조직 차원 서명을 사용 하는 것은 여기에 포함 된 내용에 관계 없이 "부인" 라고 합니다. 예를 들어 서명이 나 주소, 법적 고 지 사항 또는 원하는 기타 정보를 포함할 수도 있습니다.
    
::: moniker range="o365-worldwide"

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> 의 관리 센터로 이동합니다.

::: moniker-end

1. 앱 시작 관리자 ![ 앱 시작 관리자 아이콘 ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) 을 선택 하 고 **관리자**를 선택 합니다.
   
    찾고자 하는 앱을 찾을 수 없나요? 앱 시작 관리자에서 **모든 앱** 을 선택 하 여 사용할 수 있는 앱의 사전순 목록을 확인 합니다. 거기에서 특정 앱을 검색할 수 있습니다. 
    
2. **관리 센터**를 선택 하 고 **Exchange**를 선택 합니다.
    
3. 메일 흐름 아래에서 **규칙**을 선택 합니다.
    
4. **+**(추가) 아이콘을 선택 하 고 고 지 사항 **적용**을 선택 합니다.
    
5. 규칙 이름을 지정합니다.
    
6. **이 규칙 적용**에서 **[모든 메시지에 적용]** 을 선택 합니다.
    
    > [!TIP]
    > [자세히 알아보세요](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping). (이 범위 지정 문서는 Exchange Server에 대 한 것 이지만, Microsoft 365에도 적용 됩니다.) 
  
7. 다음 작업 실행 아래에서 **고지 사항 추가**를 선택된 상태로 둡니다. 
    
8.  **텍스트 입력** 을 선택 하 고 고 지 사항을 입력 합니다. 
    
    > [!TIP]
    > [자세히 알아보세요](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer). (이 서식 지정 문서는 Exchange Server에 대 한 것 이지만 Microsoft 365에도 적용 됩니다.) 

9. **하나 선택을** 선택 하 고 대체 항목으로 **줄 바꿈** 옵션을 선택 합니다. 그런 다음, **확인**을 선택합니다. 암호화 또는 다른 메일 설정 때문에 고지 사항을 추가할 수 없는 경우 메시지 봉투에 래핑된다는 의미입니다.
    
10. Leave **Audit this rule with severity level** selected. Then choose **Low**, **Medium**, or **High** to be used in the message log. 
    
11. 먼저 테스트하지 않고 고지 사항을 즉시 설정하려면 **적용**을 선택합니다. 
    
12. 추가 조건 또는 예외 사항을 포함하려면 **추가 옵션**을 선택합니다. 
    
13. 완료되면 **저장**을 선택합니다. 
    
## <a name="limitations-of-organization-wide-signatures"></a>조직의 광범위 서명 제한 사항

Microsoft 365 서명을 사용 하 여 다음을 수행할 수는 없습니다.
  
- 최신 전자 메일 회신이 나 forward 바로 아래에 서명 삽입
    
- 사용자의 보낸 편지함 폴더에 서버 쪽 전자 메일 서명 표시
    
- 전자 메일 서명에 이미지 포함
    
- 업데이트할 수 없는 변수가 포함 된 줄 건너뛰기 (예: 사용자에 게 값을 제공 하지 않았으므로)
    
이러한 기능과 기타 기능을 얻으려면 타사 도구를 사용 합니다. **전자 메일 서명 소프트웨어**에 대 한 인터넷 검색을 수행 하세요. 이러한 공급자의 수는 Microsoft 골드 파트너가 며, 소프트웨어는 이러한 기능을 제공 합니다. 
  
## <a name="more-resources"></a>추가 리소스

- PowerShell 사용에 대 한 자세한 내용은 [Microsoft 365의 조직 전체 메시지 법적 고 지 사항, 서명, 바닥글 또는 헤더를](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) 참조 하세요. 
    

