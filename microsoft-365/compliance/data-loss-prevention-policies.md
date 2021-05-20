---
title: 데이터 손실 방지 참조
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 데이터 손실 방지 참조 자료
ms.openlocfilehash: a6dc0b2702899e05f78c54331fb33b87495672d8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572564"
---
# <a name="data-loss-prevention-reference"></a>데이터 손실 방지 참조
 
> [!IMPORTANT]
> 이 참조 항목은 더 이상 DLP(데이터 손실 방지) 정보의 기본 Microsoft 365 않습니다. DLP 콘텐츠 집합이 업데이트 및 재구성 중입니다. 이 문서에서 다루는 항목은 업데이트된 새로운 문서로 이동될 것입니다. DLP에 대한 자세한 내용은 데이터 손실 [방지에 대한 자세한 정보를 참조하세요.](dlp-learn-about-dlp.md)

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> 데이터 손실 방지 기능은 최근 Office 365 Advanced Compliance 라이선스 사용자에 대한 Microsoft Teams 채팅 및 채널 메시지에 추가되었으며, 이는 독립 실행형 옵션으로 제공되며 Office 365 E5 및 Microsoft 365 E5 규정 준수에 포함되어 있습니다. 라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a>DLP 정책 만들기 및 관리

Microsoft 365 준수 센터의 데이터 손실 방지 페이지에서 DLP 정책을 생성하고 관리할 수 있습니다.
  
![Office 365 보안 &amp; 준수 센터의 데이터 손실 방지 페이지](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
규칙을 사용하여 특정 보호 요구 사항을 충족한 다음, DLP 정책을 사용하여 특정 규정을 준수하는 데 필요한 모든 규칙과 같은 일반적인 보호 요구 사항을 그룹화할 수 있습니다.
  
예를 들어 HIPAA(Health Insurance Portability and Accountability Act)가 적용되는 정보의 현재 상태를 확인하는 데 도움이 되는 DLP 정책이 있을 수 있습니다. 해당 DLP 정책은 조직 외부의 사용자와 공유(조건)하는 중요한 정보가 포함된 모든 문서를 찾고 문서에 대한 액세스 차단 및 알림을 전송하여(작업) 모든 SharePoint Online 사이트 및 모든 비즈니스용 OneDrive 사이트(위치)에서 HIPAA 데이터(대상)를 보호하는 데 도움을 줄 수 있습니다. 해당 요구 사항은 개별 규칙으로 저장되며 관리 및 보고를 간소화하기 위해 DLP 정책으로 그룹화 됩니다.
  
![위치 및 규칙을 포함한 DLP 정책을 보여주는 다이어그램](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

Exchange에서 특정 메일 그룹을 포함하도록 선택하는 경우 DLP 정책은 해당 그룹의 구성원으로만 제한됩니다. 마찬가지로 메일 그룹을 제외하면 해당 메일 그룹의 모든 구성원이 정책 평가에서 제외됩니다. 메일 그룹의 구성원, 동적 메일 그룹, 보안 그룹에 대한 정책의 범위를 선택할 수 있습니다. DLP 정책에는 50개 이하의 이러한 포함 및 제외가 포함될 수 있습니다.

특정 SharePoint 사이트를 포함하거나 제외하도록 선택하는 경우 DLP 정책은 이러한 포함 항목 및 제외 항목을 100개까지 포함할 수 있습니다. 해당 제한 사항에도 불구하고 조직 전체의 정책이나 전체 위치에 적용되는 정책을 적용하여 해당 제한 사항을 극복할 수 있습니다.

특정 OneDrive 계정 또는 그룹을 포함하거나 제외하도록 선택하는 경우 DLP 정책에는 100개 이상의 사용자 계정 또는 50개 그룹을 포함하거나 제외로 포함할 수 있습니다.

> [!NOTE]
> 계정 또는 그룹을 사용한 비즈니스 정책 범위 지정용 OneDrive는 공개 미리 보기로 제공됩니다. 이 단계가 진행되는 동안 사용자 계정 및 그룹을 DLP 정책의 일부로 포함하거나 제외할 수 있습니다. 동일한 정책의 일부로 포함 및 제외는 모두 지원되지 않습니다.
  
### <a name="rules"></a>규칙

> [!NOTE]
> 알림을 구성하지 않은 경우 DLP 정책에 대한 기본 동작은 알림을 보내거나 트리거하는 게 아닙니다. 이는 기본 정보 유형에만 적용됩니다. 사용자 지정 정보 유형의 경우에는 정책에 정의된 작업이 없는 경우에도 시스템이 알림을 보냅니다.

규칙은 조직의 콘텐츠에 비즈니스 요구사항을 적용한 것입니다. 정책은 하나 이상의 규칙을 포함하고 각 규칙은 조건 및 작업을 구성됩니다. 각 규칙에 대해 조건이 충족되면 작업이 자동으로 수행됩니다. 규칙은 각 정책에서 가장 우선순위가 높은 규칙부터 순차적으로 실행됩니다.
  
또한 규칙은 사용자(정책 팁 및 전자메일 알림 포함) 및 관리자(전자메일 사고 보고서 포함)에게 콘텐츠가 규칙과 일치함을 알리는 옵션을 제공합니다.
  
다음과 같이 규칙의 구성요소 및 각각에 대한 설명이 있습니다.
  
![DLP 규칙 편집기에 대한 장](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>조건

조건은 사용자가 찾고 있는 정보의 유형과 수행하는 시기를 결정하므로 중요합니다. 예를 들어 콘텐츠에 10보다 큰 숫자를 포함하지 않고 콘텐츠가 조직 외부의 사용자와 공유되지 않는 경우에는 여권 번호를 포함하는 콘텐츠를 무시하도록 선택할 수 있습니다.
  
조건은 사용자가 찾고 있는 중요한 정보의 유형이 무엇인지와 같은 **콘텐츠** 에 중점을 두고 있습니다. 또한 문서를 공유하는 대상이 누구인지와 같은 **컨텍스트** 에 중점을 두고 있습니다. 조건을 사용하여 위험 수준마다 다른 작업을 할당할 수 있습니다. 예를 들어 내부적으로 공유하는 중요한 콘텐츠는 조직 외부의 사용자와 공유되는 중요한 콘텐츠 보다 위험성이 더 낮고 더 적은 작업이 필요할 수 있습니다. 
  
![사용 가능한 DLP 조건을 표시하는 목록](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
이제 사용 가능한 조건을 통해 다음 사항의 여부를 확인할 수 있습니다.
  
- 콘텐츠가 중요한 정보 유형을 포함합니다.
    
- 콘텐츠가 레이블을 포함합니다. 더 자세한 내용은 아래의 [DLP 정책에서 보존 레이블을 조건으로 사용하기](#using-a-retention-label-as-a-condition-in-a-dlp-policy) 장을 참고하십시오.
    
- 콘텐츠를 조직 내부 또는 외부 사용자와 공유합니다.

  > [!NOTE]
  > 호스트 조직의 Active Directory 또는 Azure Active Directory 테넌트에 게스트가 아닌 계정을 보유하고 있는 사용자는 조직 내부의 사용자로 간주됩니다.
    
#### <a name="types-of-sensitive-information"></a>중요한 정보 유형

DLP 정책은 **중요한 정보 유형** 으로 정의되어 있는 중요한 정보를 보호하는 데 도움을 줄 수 있습니다. Microsoft 365에는 신용 카드 번호, 은행 계좌 번호, 국가 ID 번호 및 여권 번호 등 사용할 준비가 된 여러 다른 영역에 대한 일반적인 여러 중요 정보 유형에 대한 정의가 포함되어 있습니다. 
  
![사용가능한 중요한 정보 유형의 목록](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
DLP 정책이 신용 카드 번호와 같은 중요한 정보 유형을 찾을 때 단순히 16자리 숫자만 찾는 것이 아닙니다. 중요한 각 정보 유형은 다음의 조합을 사용해서 정의되고 검색됩니다.
  
- 키워드.
    
- 체크섬 또는 구성의 유효성을 검사하기 위한 내부 함수입니다.
    
- 패턴 일치를 찾기 위한 정규식의 평가입니다.
    
- 기타 콘텐츠 검사.
    
성러한 정책은 사용자 작업을 중단시킬 수 있는 가양성의 수를 줄이는 동시에 DLP 검색 시 높은 수준의 정확도를 얻을 수 있도록 도와줍니다.
  
#### <a name="actions"></a>작업

콘텐츠가 규칙에서 조건과 일치하는 경우 자동으로 콘텐츠를 보호하기 위한 작업을 적용할 수 있습니다.
  
![사용 가능한 DLP 작업 목록](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
현재 사용할 수 있는 작업으로 다음과 같은 작업을 수행할 수 있습니다:
  
- **콘텐츠에 대한 액세스 제한** 필요에 따라 다음 세 가지 방법으로 콘텐츠에 대한 액세스를 제한할 수 있습니다.

  1. 모든 사용자의 콘텐츠에 대한 액세스를 제한합니다.
  2. 조직 외부 사용자의 콘텐츠에 대한 액세스를 제한합니다.
  3. "링크가 있는 모든 사용자"의 액세스를 제한합니다.

  사이트 콘텐츠의 경우, 이는 문서에 대한 사용 권한이 주 사이트 컬렉션 관리자, 문서 소유자 및 문서를 마지막에 수정한 사용자를 제외한 모든 사람들에게 제한되어 있음을 의미합니다. 해당 사용자는 문서에서 중요한 정보를 제거하거나 다른 해결 조치를 취할 수 있습니다. 문서가 규정을 준수하는 경우 원래의 사용 권한은 자동으로 복원됩니다. 문서에 대한 액세스가 차단되면 해당 문서가 사이트 라이브러리에서 특수한 정책 팁 아이콘과 함께 나타납니다. 
    
  ![문서에 액세스를 표시하는 정책 팁이 차단됩니다.](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  전자 메일 콘텐츠의 경우 이 작업은 메시지가 발송되지 않도록 차단합니다. DLP 규칙이 구성된 방식에 따라 발신자는 NDR 또는 (규칙이 알림을 사용하는 경우) 정책 팁 및/또는 전자 메일 알림을 볼 수 있습니다.
    
  ![메시지에서 인증되지 않은 수신자를 제거해야 한다는 경고](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>사용자 알림 및 사용자 재정의

알림 및 재정의를 사용하여 사용자에 DLP 정책에 대해 교육하고 작업을 차단하지 않고도 규정을 준수할 수 있도록 지원할 수 있습니다. 예를 들어 사용자가 중요한 정보를 포함하는 문서를 공유하려고 하면 DLP 정책은 전자 메일 알림을 보내고, 업무 정당성이 있을 경우 이 정책을 재정의할 수 있는 문서 라이브러리의 컨텍스트에서 정책 팁을 표시합니다.
  
![DLP 규칙 편집기의 사용자 알림 및 사용자 재정의](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
전자 메일의 경우 콘텐츠를 발송한 사람. 공유한 사람 또는 마지막으로 수정한 사람을 알릴 수 있으며, 사이트 콘텐츠의 경우 주 사이트 컬렉션 관리자 및 문서 소유자를 알릴 수 있습니다. 또한 전자 메일 알림에서 원하는 사람을 추가하거나 제거할 수 있습니다.
  
전자 메일 알림을 발송하는 것 외에도 사용자 알림에는 다음과 같은 정책 팁이 표시됩니다:
  
- Outlook 및 웹 상의 Outlook
    
- SharePoint Online 또는 비즈니스용 OneDrive 사이트에 대한 문서의 경우입니다.
    
- Excel, PowerPoint 및 Word에서 DLP 정책에 포함된 사이트에 문서가 저장되는 경우입니다.
    
전자 메일 알림 및 정책 팁은 콘텐츠가 DLP 정책과 충돌하는 이유를 설명합니다. 해당 항목을 선택하면 전자 메일 알림 및 정책 팁은 가양성을 보고하거나 업무 정당성을 제공하여 사용자가 규칙을 재정의할 수 있도록 합니다. 이를 통해 사용자에게 DLP 정책을 교육하고, 사람들이 해당 작업을 수행하지 못하도록 하는 방식으로 정책을 적용할 수 있습니다. 재정의 및 가양성에 대한 정보는 보고를 위해 기록되고(DLP 보고서에 대해서는 아래 참조) 사고 보고서(다음 섹션 참조)에 포함되므로 규정 준수 책임자는 정기적으로 이 정보를 검토할 수 있습니다.
  
다음은 비즈니스용 OneDrive 계정에서 보여지는 정책 팁의 예시입니다.
  
![OneDrive 계정의 문서에 대한 정책 팁](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 DLP 정책의 사용자 알림과 정책 팁에 대한 자세한 내용은 [알림 및 정책 팁 사용](use-notifications-and-policy-tips.md)을 참조하세요.

#### <a name="alerts-and-incident-reports"></a>경고 및 인시던트 보고서

규칙이 일치하면 규정 준수 책임자(또는 선택한 다른 사람)에게 세부 정보와 함께 경고 전자 메일을 보낼 수 있습니다. 이 경고 전자 메일에는 규정 준수 책임자가 경고 및 이벤트의 세부 정보를 볼 수 있도록 [DLP 경고 관리 대시보드](dlp-configure-view-alerts-policies.md)의 링크를 포함합니다. 대시보드에는 DLP 정책과 일치하는 세부 정보 및 검색된 중요한 콘텐츠와 함께 경고를 트리거한 이벤트의 세부 정보를 포함합니다.

또한 이벤트 세부 정보가 포함된 인시던트 보고서를 보낼 수도 있습니다. 이 보고서에는 일치된 항목에 관한 정보, 규칙과 일치한 실제 콘텐츠, 해당 콘텐츠를 마지막으로 수정한 사람이 포함됩니다. 전자 메일 메시지의 경우 보고서에는 DLP 정책과 일치하는 원본 메시지가 첨부 파일로 포함되어 있습니다.

> [!div class="mx-imgBorder"]
> ![사고 보고서를 구성하기 위한 페이지](../media/Alerts-and-incident-report.png)

DLP는 SharePoint Online 또는 비즈니스용 OneDrive의 항목과는 다른 방식으로 전자 메일을 검사합니다. SharePoint Online 및 비즈니스용 OneDrive에서 DLP는 기존 항목을 비롯하여 새 항목을 검사하고 일치하는 항목이 발견될 때마다 경고 및 인시던트 보고서를 생성합니다. Exchange Online에서 DLP는 새 전자 메일 메시지만 검사하고 정책 일치 항목이 있는 경우에 보고서를 생성합니다. DLP는 사서함이나 보관함에 저장된 기존 전자 메일 항목을 검색하거나 일치시키지 ***않습니다.***
  
## <a name="grouping-and-logical-operators"></a>그룹화 및 논리 연산자

일반적으로 DLP 정책에는 미국의 주민등록번호를 포함하는 모든 콘텐츠를 식별하는 것과 같은 간단한 요구사항을 가지고 있습니다. 하지만 다른 시나리오에서는 DLP 정책이 좀 더 느슨하게 정의된 데이터를 식별해야 할 수 있습니다.
  
예를 들어 미국 HIPAA(Health Insurance Portability and Accountability Act)를 적용받는 콘텐츠를 식별하려면 다음과 같은 정보를 찾아야 합니다:
  
- 미국 사회보장번호 또는 DEA(마약단속국) 번호와 같은 특정 유형의 중요한 정보를 포함하는 콘텐츠
    
    그리고
    
- 환자의 병력에 관한 커뮤니케이션 또는 환자에게 제공된 의료 서비스에 대한 설명과 같이 식별하기 더 어려운 콘텐츠 해당 콘텐츠를 식별하려면 국제질병분류(ICD-9-CM 또는 ICD-10-CM)처럼 아주 방대한 키워드 목록에서 일치하는 키워드가 필요합니다.
    
이렇게 느슨하게 정의된 데이터는 그룹화 및 논리 연산자(AND, OR)를 사용하여 쉽게 식별할 수 있습니다. DLP 정책을 만들 때는
  
- 중요한 정보 유형을 그룹화할 수 있습니다.
    
- 그룹에 포함된 중요한 정보 사이에 사용할 논리 연산자와 각 그룹 사이에 사용할 논리 연산자를 선택할 수 있습니다.
    
### <a name="choosing-the-operator-within-a-group"></a>그룹 내의 연산자 선택

그룹 내에서 콘텐츠가 규칙에 일치하려면 해당 그룹의 조건을 모두 충족해야 하는지 또는 하나라도 충족하면 되는지 선택할 수 있습니다.
  
![그룹 내의 연산자가 표시된 그룹](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>그룹 추가

그룹을 빠르게 추가할 수 있습니다. 그룹은 자체적인 조건과 연산자를 가질 수 있습니다.
  
![그룹 단추 추가](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>그룹 사이의 연산자 선택

각 그룹 사이에서 콘텐츠가 규칙에 매칭되려면 그룹 하나의 조건만 충족해야 하는지 또는 모든 그룹의 조건을 충족해야 하는지 선택할 수 있습니다.
  
예를 들어 기본 제공되는 **미국 HIPAA** 정책에는 그룹 사이에서 **AND** 연산자를 사용하여 다음과 같은 정보가 포함된 콘텐츠를 식별하는 규칙이 있습니다. 
  
- 그룹 **PII 식별자** 에서(하나 이상의 SSN 번호 **또는** DEA 번호) 
    
    **AND**
    
- 그룹 **의료 조건** 에서(하나 이상의 ICD-9-CM 키워드 **또는** ICD-10-CM 키워드) 
    
![각 그룹 사이의 연산자가 표시된 그룹](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>규칙이 처리되는 우선 순위

정책의 규칙을 만들 때는 각 규칙에 만들어진 순서대로 우선 순위가 할당됩니다. 즉, 처음 만들어진 규칙에는 첫 번째 우선 순위가 할당되고 두 번째 만들어진 규칙에는 두 번째 우선 순위가 할당되는 식입니다.

> [!div class="mx-imgBorder"]
> ![우선 순위의 규칙](../media/dlp-rules-in-priority-order.png)
  
둘 이상의 DLP 정책을 설정한 후에는 하나 이상의 정책에 대해 우선 순위를 변경할 수 있습니다. 그러기 위해서는 정책을 선택하고 **정책 편집** 을 선택한 다음 **우선 순위** 목록을 사용하여 우선 순위를 지정합니다.

> [!div class="mx-imgBorder"]
> ![정책에 대한 우선 순위 설정](../media/dlp-set-policy-priority.png)

콘텐츠를 규칙에 대해 평가할 때 규칙은 우선 순위대로 처리됩니다. 콘텐츠가 여러 규칙과 일치하는 경우 규칙은 우선 순위대로 처리되고 가장 제한적인 작업이 적용됩니다. 예를 들어 콘텐츠가 다음과 같은 규칙과 모두 일치하는 경우 우선 순위가 가장 높고 가장 제한적인 규칙 3이 적용됩니다:
  
- 규칙 1: 사용자에게 알리기만 함
    
- 규칙 2: 사용자에게 알리고, 액세스를 제한하고, 사용자 재정의를 허용함
    
- 규칙 3: 사용자에게 알리고, 액세스를 제한하고, 사용자 재정의를 허용하지 않음
    
- 규칙 4: 사용자에게 알리기만 함
    
- 규칙 5: 액세스를 제한함
    
- 규칙 6: 사용자에게 알리고, 액세스를 제한하고, 사용자 재정의를 허용하지 않음
    
이 예시에서 가장 제한적인 규칙만 적용되더라도 모든 규칙에 대한 일치 항목이 감사 로그에 기록되고 DLP 보고서에 표시됩니다.
  
정책 팁에 대한 자세한 내용은 다음을 참고하십시오:
  
- 가장 높은 우선 순위와 가장 제한적인 규칙의 정책 팁만 표시됩니다. 예를 들어 알림을 콘텐츠 액세스를 차단하는 규칙의 정책 팁은 단순히 알림을 보내는 규칙의 정책 팁보다 우선적으로 표시됩니다. 따라서 정책 팁이 단계별로 표시되지는 않습니다.
    
- 가장 제한적인 규칙의 정책 팁이 사용자의 규칙 재정의를 허용할 경우 이 규칙을 재정의하면 해당 콘텐츠가 일치하는 다른 모든 규칙이 함께 재정의됩니다.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>더 쉽게 또는 더 어렵게 일치하도록 규칙 조정

DLP 정책을 만들고 설정한 후에 다음과 같은 문제가 발생하기도 합니다:
  
- 중요한 정보가 **아닌** 콘텐츠가 규칙과 너무 많이 일치합니다. 즉, 가양성이 너무 많습니다. 
    
- 중요한 정보가 **있는** 콘텐츠 중 규칙과 일치하는 콘텐츠가 너무 적습니다. 즉, 중요한 정보에 대한 보호 조치가 적용되고 있지 않습니다. 
    
이러한 문제를 해결하려면 콘텐츠가 규칙과 더 어렵게 또는 더 쉽게 일치하도록 인스턴스 수와 일치 정확도를 조정하여 규칙을 조정할 수 있습니다. 규칙에 사용되는 각 중요한 정보 유형에는 인스턴스 수와 일치 정확도가 둘 다 포함됩니다.
  
### <a name="instance-count"></a>인스턴스 수

인스턴스 수는 콘텐츠가 규칙과 일치하기 위해 있어야 하는 특정 중요한 정보 유형의 발생 횟수를 의미합니다. 예를 들어, 다음의 경우에 아래와 같이 콘텐츠가 규칙에 일치합니다. 콘텐츠가 1에서 9사이의 고유한 미국 또는 영국의 여권 번호를 식별하는 경우.

> [!NOTE]
> 인스턴스 수에는 중요한 정보 유형 및 키워드에 대해 **고유한** 일치 항목만 포함됩니다. 예를 들어 전자 메일에 동일한 신용 카드 번호가 10번 포함되는 경우 해당 10번은 신용 카드 번호의 단일 인스턴스로 계산됩니다.
  
인스턴스 수를 사용하여 규칙을 조정하려는 경우 지침은 다음과 같이 간단합니다:
  
- 규칙이 더 쉽게 일치하도록 하려면 **최소** 개수를 줄이고(줄이거나) **최대** 개수를 늘립니다. 숫자 값을 삭제하여 **최대** 를 **모두** 로 설정할 수도 있습니다. 
    
- 규칙이 더 어렵게 일치하도록 하려면 **최소** 개수를 늘립니다. 
    
일반적으로 인스턴스 수가 낮은(예: 1-9) 규칙에서는 덜 제한적인 작업(예: 사용자 알림 보내기)을 사용합니다. 또한 인스턴스 수가 높은(예: 10-모두) 규칙에서는 더 제한적인 작업(예: 사용자 재정의를 허용하지 않고 콘텐츠에 대한 액세스 제한)을 사용합니다.
  
![규칙 편집기의 인스턴스 수](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>일치 정확도

위에서 설명한 것처럼, 중요한 정보 유형은 다양한 유형의 증거 결합을 통해 정의되고 검색됩니다. 일반적으로 중요한 정보 유형은 패턴이라는 이러한 여러 결합으로 정의됩니다. 증거가 덜 필요한 패턴은 일치 정확도(또는 신뢰 수준)가 낮은 데 반해 증거가 더 필요한 패턴은 일치 정확도(또는 신뢰 수준)가 높습니다. 모든 중요한 정보 유형에서 사용되는 실제 패턴 및 신뢰 수준에 대해 자세히 알아보려면 [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.
  
예를 들어 신용 카드 번호라는 중요한 정보 유형은 다음과 같은 두 개의 패턴으로 정의됩니다.
  
- 다음이 필요한 65% 신뢰의 패턴:
    
  - 신용 카드 번호 형식의 숫자
    
  - 체크섬을 전달하는 숫자
    
- 다음이 필요한 85% 신뢰의 패턴:
    
  - 신용 카드 번호 형식의 숫자
    
  - 체크섬을 전달하는 숫자
    
  - 올바른 형식의 키워드 또는 만료 날짜
    
규칙에서 이러한 신뢰 수준(또는 일치 정확도)을 사용할 수 있습니다. 일반적으로 일치 정확도가 낮은 규칙에서는 덜 제한적인 작업(예: 사용자 알림 보내기)을 사용합니다. 또한 일치 정확도가 높은 규칙에서는 더 제한적인 작업(예: 사용자 재정의를 허용하지 않고 콘텐츠에 대한 액세스 제한)을 사용합니다.
  
콘텐츠에서 특정 중요한 정보 유형(예: 신용 카드 번호)이 식별되면 하나의 신뢰 수준만 반환된다는 사실을 이해해야 합니다:
  
- 모든 일치 항목이 단일 패턴인 경우 해당 패턴의 신뢰 수준이 반환됩니다.
    
- 두 개 이상의 패턴에 대한 일치 항목이 있는 경우(즉, 서로 다른 두 가지 신뢰 수준의 일치 항목이 있는 경우) 모든 단일 패턴보다 높은 신뢰 수준만 반환됩니다. 이는 까다로운 부분입니다. 예를 들어 신용 카드의 경우 65% 패턴과 85% 패턴이 둘 다 일치하면 더 많은 증거가 더 높은 신뢰를 의미하므로 해당 중요한 정보 유형에 대해 반환되는 신뢰 수준은 90%보다 높습니다.
    
따라서 신용 카드에 대한 상호 배타적인 두 가지 규칙(65% 일치 정확도에 대한 규칙 하나와 85% 일치 정확도에 대한 규칙 하나)을 만들려는 경우 일치 정확도의 범위는 다음과 같습니다. 첫 번째 규칙에서는 65% 패턴의 일치 항목만 선택합니다. 두 번째 규칙에서는 **하나 이상의** 85% 일치 항목을 선택하며 다른 낮은 신뢰의 일치 항목이 **잠재적으로 있을 수 있습니다.** 
  
![일치 정확도에 대한 서로 다른 범위가 포함된 두 개의 규칙](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
해당 이유로 서로 다른 일치 정확도가 있는 규칙을 만들 때의 지침은 다음과 같습니다:
  
- 일반적으로 가장 낮은 신뢰 수준에서는 **최소** 와 **최대**(범위 아님)에 같은 값을 사용합니다. 
    
- 일반적으로 가장 높은 신뢰 수준은 낮은 신뢰 수준 바로 위에서 100까지의 범위입니다.
    
- 일반적으로 그 사이에 있는 모든 신뢰 수준은 낮은 신뢰 수준 바로 위에서 높은 신뢰 수준 바로 아래까지의 범위입니다.
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>보존 레이블을 DLP 정책의 조건으로 사용

DLP 정책에서 이전에 생성 및 게시 된 [보존 레이블](retention.md#retention-labels)을 조건으로 사용하는 경우 다음 사항에 유의해야 합니다.

- DLP 정책의 조건으로 사용하기 전 미리 보존 레이블을 작성 및 게시해야 합니다.
- 게시한 보존 레이블이 동기화되기까지 1일에서 7일까지 걸릴 수 있습니다. 자세한 내용은 보존 정책 형태로 게시되는 보존 레이블에 대한 [보존 레이블을 적용할 수 있게 되는 때](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) 및 자동 게시되는 보존 레이블에 대한 [보존 레이블이 유효해지는 데 걸리는 시간](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect)을 참조하세요.
- 정책** 형태로 보존 레이블 사용하기는 SharePoint 및 OneDrive***의 항목에 한해 지원됩니다.

  ![조건으로서의 레이블](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  보존 및 처리 중인 항목이 있고 다른 컨트롤을 적용하려는 경우 DLP 정책에 보존 레이블을 사용할 수 있습니다. 예를 들면 다음과 같습니다.

  - **과세 연도 2018** 이라는 보존 레이블을 게시했으며, 2018년에 과세 문서에 적용할 때 SharePoint에 저장된 10년 동안 보관한 다음 폐기합니다. 또한 DLP 정책으로 수행할 수 있는 항목을 조직 외부에서 공유하고 싶지 않습니다.

  > [!IMPORTANT]
  > DLP 정책에서 보존 레이블을 조건으로 지정하고 Exchange 및/또는 Teams를 위치로 포함하면 이 오류가 발생합니다. **"전자 메일 및 팀 메시지에서 레이블이 지정된 콘텐츠를 보호할 수 없습니다. 아래의 레이블을 제거하거나 Exchange 및 Teams를 위치로 사용하는 것을 중지하세요."** 이는 Exchange 전송에서 메시지 제출 및 배달이 진행되는 동안 레이블 메타 데이터를 평가하지 않기 때문입니다. 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a>민감도 레이블을 DLP 정책의 조건으로 사용

[DLP 정책에서](./dlp-sensitivity-label-as-condition.md) 민감도 레이블을 조건으로 사용하는 방법을 자세히 알아보습니다.
  
### <a name="how-this-feature-relates-to-other-features"></a>해당 기능이 다른 기능과 관련되는 방식

중요한 정보를 포함하는 콘텐츠에 다음과 같은 몇 가지 기능을 적용할 수 있습니다:
  
- [보존 레이블 및 보존 정책](retention.md) 모두 해당 콘텐츠에서 **보존** 작업을 적용할 수 있습니다. 
    
- DLP 정책은 해당 콘텐츠에 **보호** 작업을 적용할 수 있습니다. 또한 이러한 작업을 적용하기 전에 DLP 정책은 레이블을 포함하는 콘텐츠 외에 다른 조건이 충족되도록 요구할 수 있습니다. 
    
![중요한 정보에 적용할 수 있는 기능의 다이어그램](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
DLP 정책은 중요한 정보에 적용된 레이블 또는 보존 정책보다 풍부한 검색 기능을 갖습니다. DLP 정책은 중요한 정보를 포함하는 콘텐츠에 보호 작업을 적용할 수 있으며, 콘텐츠에서 중요한 정보가 제거되면 다음에 콘텐츠가 검색될 때 해당 보호 작업이 실행 취소됩니다. 그러나 중요한 정보를 포함하는 콘텐츠에 보존 정책 또는 레이블이 적용되면, 해당 적용은 중요한 정보가 제거되더라도 실행 취소되지 않는 일회성 작업입니다.
  
레이블을 DLP 정책에서 조건으로 사용하여 해당 레이블이 있는 콘텐츠에 보존 작업과 보호 작업을 둘 다 적용할 수 있습니다. 레이블을 포함하는 콘텐츠를 중요한 정보를 포함하는 콘텐츠와 정확히 같은 것으로 생각할 수 있습니다. 레이블 및 중요한 정보 유형은 콘텐츠에 작업을 적용할 수 있도록 해당 콘텐츠를 분류하는 데 사용되는 속성입니다.
  
![레이블을 조건으로 사용하는 DLP 정책의 다이어그램](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>간단한 설정과 고급 설정

DLP 정책을 생성할 때 간단한 설정과 고급 설정 중 하나를 선택하게 됩니다.
  
- **간단한 설정** 을 사용하면 규칙 편집기를 사용하여 규칙을 만들거나 수정하지 않고도 대부분의 일반적인 유형의 DLP 정책을 손쉽게 만들 수 있습니다. 
    
- **고급 설정** 을 사용하면 규칙 편집기로 DLP 정책의 모든 설정을 제어할 수 있습니다. 
    
걱정할 필요 없습니다. 간단한 설정과 고급 설정은 조건과 작업으로 구성된 규칙을 적용한다는 점에서 동일합니다. 간단한 설정에서는 규칙 편집기를 볼 수 없다는 점이 다릅니다. 간단한 설정을 사용하면 빠르고 간편하게 DLP 정책을 만들 수 있습니다.
  
### <a name="simple-settings"></a>간단한 설정

가장 일반적인 DLP 시나리오는 중요한 정보가 포함된 콘텐츠가 조직 밖의 사용자와 공유되지 않도록 보호하고, 콘텐츠에 액세스할 수 있는 사용자를 제한하거나, 최종 사용자 또는 관리자 알림을 발송하거나, 향후 조사를 위해 이벤트 감사를 수행하는 등의 자동 시정 조치를 취하는 정책을 만드는 것입니다. DLP는 중요한 정보가 우발적으로 공개되지 않도록 방지하는 데 사용됩니다.
  
DLP 정책을 만들 때 **간단한 설정 사용** 을 선택하면 이러한 목적을 간편하게 달성할 수 있습니다. 간단한 설정에서는 규칙 편집기를 사용하지 않고도 대부분의 일반적인 DLP 정책을 구현하는 데 필요한 모든 것을 사용할 수 있습니다.
  
![기본 설정 및 고급 설정의 DLP 옵션](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>고급 설정

사용자 지정 DLP 정책을 만들어야 하는 경우에는 **고급 설정 사용** 을 선택합니다.
  
고급 설정에서는 규칙 편집기를 사용하여 인스턴스 개수, 각 규칙의 일치 정확도(신뢰도 수준)를 비롯한 모든 옵션을 제어할 수 있습니다.
  
특정 장으로 건너뛰려면 규칙 편집기 상단의 탐색에 있는 항목을 클릭하여 해당 장으로 이동합니다.
  
![DLP 규칙 편집기의 상단 탐색 모음](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>DLP 정책 템플릿

DLP 정책을 생성하는 첫 번째 단계는 보호할 정보를 선택하는 것입니다. DLP 템플릿을 사용하여 새로운 규칙 집합을 처음부터 새로 작성하고 기본적으로 포함해야 하는 정보 유형을 고민하는 데 필요한 시간이 단축됩니다. 그런 다음 조직의 특정 요구 사항에 맞게 해당 요구 사항을 추가하거나 수정하여 규칙을 미세 조정할 수 있습니다.
  
미리 구성된 DLP 정책 템플릿은 HIPAA 데이터, PCI-DSS 데이터, 금융서비스 현대화법(Gramm-Leach-Bliley Act) 데이터 또는 고유 PII(개인 식별 정보)와 같은 특정 유형의 중요한 정보를 검색하는 데 도움이 될 수 있습니다. 일반적인 유형의 중요한 정보를 쉽게 찾아 보호할 수 있도록 하기 위해 Microsoft 365에 포함된 정책 템플릿에는 이미 시작하는 데 필요한 가장 일반적인 중요한 정보 유형이 포함되어 있습니다.
  
![미국 애국자법을 위한 템플릿에 중점을 두는 데이터 손실 방지 정책에 대한 템플릿 목록](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
조직에 고유한 요구 사항이 있을 경우 **사용자 지정 정책** 옵션을 선택하여 DLP 정책을 처음부터 새로 만들 수 있습니다. 사용자 지정 정책은 비어 있으며, 미리 구성된 규칙이 포함되어 있지 않습니다. 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a>DLP 보고서

DLP 정책을 만들고 설정한 후에는 의도한 대로 작동하는지와 규정 준수 상태를 유지하는 데 도움이 되는지 확인할 수 있습니다. DLP 보고서를 사용하면 시간에 따른 DLP 정책 및 규칙 일치 수와 가양성 및 재정의 수를 빠르게 확인할 수 있습니다. 각 보고서에 대해 위치, 시간 프레임에 따라 일치하는 항목을 필터링할 수 있으며 특정 정책, 규칙 또는 작업으로 범위를 좁힐 수도 있습니다.
  
DLP 보고서를 사용하면 비즈니스 통찰력을 얻고 다음을 수행할 수 있습니다.
  
- 특정 기간에 초점을 맞추고 스파이크 및 추세의 이유를 이해합니다.
    
- 조직의 규정 준수 정책을 위반하는 비즈니스 프로세스를 검색합니다.
    
- DLP 정책이 비즈니스에 미치는 영향을 이해합니다.
    
또한 DLP 보고서를 사용하여 실행 중에 DLP 정책을 미세 조정할 수 있습니다.
  
![보안 및 규정 준수 센터의 보고서 대시보드](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>DLP 정책이 작동하는 방식

DLP는 심도 깊은 콘텐츠 분석(단순 텍스트 검색 아님)을 사용하여 중요한 정보를 검색합니다. 이 심도 깊은 콘텐츠 분석은 키워드 일치, 사전 일치, 정규식 평가, 내부 함수 및 기타 방법을 사용하여 DLP 정책과 일치하는 콘텐츠를 검색합니다. 잠재적으로 데이터의 일부만 중요한 것으로 간주됩니다. DLP 정책은 나머지 콘텐츠로 작업하는 사람들에게 영향을 주거나 작업을 지연시키지 않으면서 해당 데이터를 식별 및 모니터링하고 자동으로 보호할 수 있습니다.
  
### <a name="policies-are-synced"></a>정책이 동기화됨

보안 &amp; 규정 준수 센터에서 DLP 정책을 만든 후 정책은 중앙 정책 저장소에 저장되며 다음을 포함하는 다양한 콘텐츠 원본과 동기화합니다:
  
- Exchange Online, 웹용 Outlook 및 Outlook.
    
- 비즈니스용 OneDrive 사이트.
    
- SharePoint Online 사이트.
    
- Office 데스크톱 프로그램 (Excel, PowerPoint 및 Word).

- Microsoft Teams 채널 및 채팅 메시지.
    
정책이 올바른 위치와 동기화된 후 콘텐츠를 평가하고 작업을 적용하기 시작합니다.
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>비즈니스용 OneDrive 및 SharePoint Online 사이트에서의 정책 평가

SharePoint Online 사이트 및 비즈니스용 OneDrive 사이트 전체에 걸쳐 문서는 지속적으로 변경됩니다. 즉 계속해서 생성되고, 편집되고, 공유됩니다. 즉, 문서는 언제든지 DLP 정책과 충돌을 일으키거나 정책을 준수할 수 있습니다. 예를 들어 한 사람이 자신의 팀 사이트에 중요한 정보를 포함하지 않는 문서를 업로드할 수 있습니다. 하지만 후에 다른 사람이 같은 문서를 편집하고 중요한 정보를 추가할 수 있습니다.
  
이러한 이유로 DLP 정책은 백그라운드에서 문서의 정책 일치 여부를 자주 확인합니다. 이러한 검사를 비동기 정책 평가로 간주할 수 있습니다.<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>작업 방법
 
사용자가 사이트에서 문서를 추가하거나 변경하면 검색 엔진에서 콘텐츠를 검색하여 나중에 검색할 수 있도록 합니다. 이 과정이 진행되는 동안 콘텐츠에 중요한 정보가 있는지 그리고 공유되고 있는지 검색합니다. 발견된 모든 중요한 정보는 검색 인덱스에 안전하게 저장되므로, 일반 사용자가 아닌 규정 준수 팀만 액세스할 수 있습니다. 사용자가 설정한 각 DLP 정책은 백그라운드에서(비동기적) 실행되며 정책과 일치하는 모든 콘텐츠를 자주 검색하고 부주의한 누설이 일어나지 않도록 방지하는 작업을 적용합니다.
  
![DLP 정책에서 콘텐츠를 비동기적으로 평가하는 방법을 보여주는 다이어그램](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --> 마지막으로 문서는 DLP 정책과 충돌할 수 있지만 DLP 정책을 준수할 수도 있습니다. 예를 들어 어떤 사람이 신용 카드 번호를 문서를 추가하는 경우 DLP 정책이 문서에 대한 액세스를 자동으로 차단할 수 있습니다. 하지만 나중에 이 사람이 중요한 정보를 제거하면 다음 번에 정책에 대해 문서가 평가될 때 작업(이 경우 차단)이 자동으로 실행 취소됩니다.
  
DLP는 인덱스를 지정할 수 있는 모든 콘텐츠를 평가합니다. 기본적으로 크롤링되는 파일 형식에 대한 자세한 내용은 [SharePoint Server의 크롤링되는 기본 파일 이름의 확장명 및 구문 분석되는 파일 형식](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)을 참고하십시오.

> [!NOTE]
> DLP 정책이 문서를 분석하기 전에 문서를 공유하지 못하게 하기 위해 콘텐츠가 인덱싱될 때까지 SharePoint 파일의 공유를 차단할 수 있습니다. 자세한 내용은 [신규 파일을 기본으로 민감하게 설정하기](/sharepoint/sensitive-by-default)를 참고하세요. 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Exchange, Outlook 및 웹 상 Outlook의 정책 평가

Exchange Online을 위치로 포함 하는 DLP 정책을 만드는 경우 해당 정책은 Office 365 보안 &amp; 준수 센터에서 Exchange Online으로 동기화 된 후 Exchange Online에서 웹 상 Outlook 및 Outlook으로 동기화 됩니다.
  
Outlook에서 메시지를 작성할 때 생성 중인 콘텐츠가 DLP 정책을 기준으로 평가됨에 따라 사용자에게 정책 팁이 표시됩니다. 메시지가 발생하면 정상적인 메일 흐름의 일부로서 DLP 정책을 기준으로 평가되며, 이와 함께 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)과 Exchange 관리 센터에서 생성된 DLP 정책을 기준으로 평가됩니다. DLP 정책은 메시지와 첨부 파일을 모두 검색합니다.
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Office 데스크톱 프로그램의 정책 평가

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel, PowerPoint 및 Word에는 중요한 정보를 식별하고 DLP 정책을 적용하는 SharePoint Online 및 비즈니스용 OneDrive와 동일한 기능이 있습니다. 해당 Office 프로그램은 중앙 정책 저장소에서 직접 해당 DLP 정책을 동기화한 후 사용자들이 DLP 정책에 포함된 사이트에서 연 문서로 작업할 때 DLP 정책을 기준으로 콘텐츠를 지속적으로 평가합니다.
  
Office의 DLP 정책 평가는 해당 콘텐츠를 사용하는 프로그램의 성능이나 사용자의 생산성에 영향을 미치지 않도록 고안되었습니다. 규모가 큰 문서에서 작업 중이거나 사용자의 컴퓨터가 다른 작업 중인 경우 정책 팁이 표시되는 데 몇 초 정도 걸릴 수 있습니다.

### <a name="policy-evaluation-in-microsoft-teams"></a>Microsoft Teams의 정책 평가
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

Microsoft Teams를 위치로 포함하는 DLP 정책을 만드는 경우 해당 정책은 Office 365 보안 &amp; 준수 센터에서 사용자 계정 및 Microsoft Teams 채널과 채팅 메시지와 동기화 됩니다. DLP 정책을 구성 하는 방법에 따라 제3자가 Microsoft Teams 채팅 또는 채널 메시지에서 중요한 정보를 공유하려고 시도하는 경우 메시지가 차단되거나 취소될 수 있습니다. 그리고 중요한 정보를 포함하고 게스트(외부 사용자)와 공유되는 문서가 해당 사용자에게 열리지 않습니다. 더 자세한 내용은 [데이터 손실 방지 및 Microsoft Teams](dlp-microsoft-teams.md)를 참고하십시오.
 
## <a name="permissions"></a>사용 권한

DLP 정책을 만드는 규정 준수 팀의 구성원에게는 보안 &amp; 준수 센터에 대한 사용 권한이 필요합니다. 기본적으로 테넌트 관리자는 해당 위치에 액세스할 수 있으며, 테넌트 관리자의 사용 권한을 모두 주지 않으면서 준수 관리자 및 기타 사용자에게 보안 &amp; 준수 센터에 대한 액세스 권한을 부여할 수 있습니다. 이를 위해, 다음의 단계가 권장됩니다:
  
1. Microsoft 365에서 그룹을 생성하고 규정 준수 책임자를 추가하십시오.
    
2. 보안 &amp; 준수 센터의 **사용 권한** 페이지에서 역할 그룹을 생성하십시오. 

3. 역할 그룹을 만드는 동안 **역할 선택** 섹션을 사용하여 역할 그룹에 **DLP 준수 관리** 역할을 추가합니다.
    
4. **구성원 선택** 섹션을 사용하여 이전에 만든 Microsoft 365 그룹을 역할 그룹에 추가합니다.

**보기 전용 DLP 준수 관리** 역할을 부여하여 DLP 정책 및 DLP 보고서에 대한 보기 전용 권한이 있는 역할 그룹을 만들 수도 있습니다.

더 자세한 내용은 [Office 365 준수 센터 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참고하십시오.
  
이러한 정책은 DLP 정책을 만들고 적용하는 데만 필요합니다. 정책 적용을 위해서는 콘텐츠에 액세스하지 않아도 됩니다.
  
## <a name="find-the-dlp-cmdlets"></a>DLP cmdlet 찾기

대부분의 보안 &amp; 준수 센터용 cmdlet을 사용하려면 다음의 단계를 따르십시오:
  
1. [원격 PowerShell을 사용하여 Office 365 보안 &amp; 준수 센터에 연결](/powershell/exchange/connect-to-scc-powershell)
    
2. 이 [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection) 중 하나를 사용하십시오.
    
하지만 DLP 보고서에서는 Exchange Online을 포함한 Microsoft 365에서 데이터를 가져와야 합니다. 이러한 이유로 **DLP 보고서용 cmdlet은 보안 &amp; 준수 센터 Powershell이 아닌 Exchange Online Powershell에서 사용할 수 있습니다.** 따라서 DLP 보고서용 cmdlet을 사용하려면 다음의 단계가 필요합니다:
  
1. [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)합니다.
    
2. 다음과 같은 DLP 보고서용 cmdlet 중 하나 사용
    
    - [Get-DlpDetectionsReport](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [Get-DlpDetailReport](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a>추가 정보

- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
    
- [DLP 정책에 대한 알림을 보내고 정책 팁 표시](use-notifications-and-policy-tips.md)
    
- [FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기](protect-documents-that-have-fci-or-other-properties.md)
    
- [DLP 정책 템플릿에 포함되는 내용](what-the-dlp-policy-templates-include.md)
    
- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
    
- [DLP 함수가 찾는 항목](what-the-dlp-functions-look-for.md)
    
- [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)
