---
title: 조직 전체의 서명 및 고지 조항 만들기
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
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 조직으로 들어오거나 조직에서 나가는 모든 전자 메일 메시지에 대한 법적 고지 조항 또는 공개 설명을 포함하여 전자 메일 서명을 관리하는 방법을 학습합니다.
ms.openlocfilehash: c8d63a11a75b9b53de9cabdf1f4baabc61cc3e42
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926921"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>조직 전체의 서명 및 고지 조항 만들기

 조직에 들어오거나 조직에서 나가는 전자 메일 메시지에 전자 메일 서명, 법적 고지 조항 또는 공개 문을 추가하여 전자 메일 서명을 관리할 수 있습니다. 아래에 표시된 것처럼 모든 수신 및 발신 메시지에 적용하도록 설정할 수 있습니다. 특정 단어나 텍스트 패턴이 포함된 메시지처럼 특정 메시지에 적용할 수도 있습니다.

 회사 전체의 전자 메일 서명을 만드는 데 대한 짧은 비디오를 시청하세요. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.

## <a name="create-a-signature-that-applies-to-all-messages"></a>모든 메시지에 적용되는 서명 만들기

> [!TIP]
> 조직 전체 서명은 포함된 문서에 관계없이 "고지"라고 합니다. 예를 들어 서명일 뿐일 수도, 주소, 법적 고지 조항 또는 원하는 기타 정보도 포함할 수 있습니다.
    
::: moniker range="o365-worldwide"

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> 의 관리 센터로 이동합니다.

::: moniker-end

1. 앱 시작 관리자 앱 시작 관리자 아이콘을 선택한 다음 ![ ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) 관리자를 **선택합니다.**
   
    찾고자 하는 앱을 찾을 수 없나요? 앱 시작기에서 모든  앱을 선택하여 사용할 수 있는 앱의 사전순 목록을 볼 수 있습니다. 거기에서 특정 앱을 검색할 수 있습니다. 
    
2. 관리 **센터를 선택한** 다음 **Exchange를 선택합니다.**
    
3. 메일 흐름에서 **규칙을 선택합니다.**
    
4. Select the **+** (Add) icon and choose **Apply Disclaimers.**
    
5. 규칙 이름을 지정합니다.
    
6. 이 **규칙 적용 아래에서** **[모든 메시지에 적용]을 선택합니다.**
    
    > [!TIP]
    > [자세히 알아보세요](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping). (이 문서의 전체 Exchange Server Microsoft 365에도 적용됩니다.) 
  
7. 다음 작업 실행 아래에서 **고지 사항 추가** 를 선택된 상태로 둡니다. 
    
8.  텍스트 **입력을 선택하고** 고지 조항을 입력합니다. 
    
    > [!TIP]
    > [자세히 알아보세요](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer). (이 서식 문서는 Exchange Server Microsoft 365에도 적용됩니다.) 

9. 하나를 **선택하고** **다른 옵션으로 줄** 바꿈을 선택합니다. 그런 다음, **확인** 을 선택합니다. 암호화 또는 다른 메일 설정 때문에 고지 사항을 추가할 수 없는 경우 메시지 봉투에 래핑된다는 의미입니다.
    
10. **심각도 수준으로 이 규칙 감사** 를 선택된 채로 둡니다. 그런 다음, 메시지 로그에 사용될 **낮음**, **중간** 또는 **높음** 을 선택합니다. 
    
11. 먼저 테스트하지 않고 고지 사항을 즉시 설정하려면 **적용** 을 선택합니다. 
    
12. 추가 조건 또는 예외 사항을 포함하려면 **추가 옵션** 을 선택합니다. 
    
13. 완료되면 **저장** 을 선택합니다. 
    
## <a name="limitations-of-organization-wide-signatures"></a>조직 전체 서명의 제한 사항

Microsoft 365에서 전자 메일 서명을 관리할 때 다음을 할 수 없습니다.
  
- 최신 전자 메일 회신 또는 전달 바로 아래에 서명 삽입
    
- 사용자의 보낸 항목 폴더에 서버 쪽 전자 메일 서명 표시
    
- 전자 메일 서명에 이미지 추가
    
- 업데이트할 수 없는 변수가 포함된 건너뛰기 줄(예: 사용자에게 값을 제공하지 않은 경우)
    
이러한 기능과 기타 기능을 통해 전자 메일 서명을 관리하려면 타사 도구를 사용합니다. 전자 메일 서명 소프트웨어에 대한 인터넷 **검색을 하세요.** 이러한 공급자 중 다수는 Microsoft Gold 파트너이자 해당 소프트웨어가 이러한 기능을 제공합니다. 
  
## <a name="more-resources"></a>추가 리소스

- PowerShell 사용에 대한 자세한 내용은 Exchange Online의 조직 전체 메시지 고지, [서명, 머리글](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) 또는 머리글을 참조하세요.