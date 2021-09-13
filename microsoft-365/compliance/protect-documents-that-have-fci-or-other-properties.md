---
title: FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
description: DLP(데이터 손실 방지) 정책을 사용하여 타사 시스템의 속성이 있는 문서를 보호하는 방법을 학습합니다.
ms.openlocfilehash: 60440162834bbef34c6e3adc2a60053cd9015e9d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221104"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기

Microsoft 365 DLP(데이터 손실 방지) 정책은 분류 속성 또는 항목 속성을 사용하여 중요한 항목을 식별할 수 있습니다. 예를 들어 다음을 사용할 수 있습니다.

- Windows FCI(서버 파일 분류 인프라) 속성
- SharePoint 속성
- 타사 시스템 문서 속성

![Office 365 및 외부 분류 시스템을 보여주는 다이어그램입니다.](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

예를 들어 조직에서는 Windows Server FCI를 사용하여 주민 등록 번호와 같은 개인 데이터가 있는 항목을  식별한 다음 개인 식별 정보 속성을 문서에서 찾은 개인 데이터의 유형과 횟수에 따라 높음, 보통, 낮음, 공용 또는 **PII** 아예로 설정하여 문서를 분류할 수 있습니다.   

이 Microsoft 365 속성이 **High** 및 **Medium과** 같은 특정 값으로 설정된 문서를 식별하는 DLP 정책을 만든 다음 해당 파일에 대한 액세스를 차단하는 등의 작업을 취할 수 있습니다. 해당 속성이 **낮음** 으로 설정된 경우에는 전자 메일 알림 전송 등의 다른 작업을 수행하는 다른 규칙을 동일한 정책에 만들 수도 있습니다. 이러한 방식으로 DLP는 Windows Server FCI와 통합되어 Office 서버 기반 파일 서버에서 Microsoft 365 공유되는 Windows 보호할 수 있습니다.

DLP 정책은 단순히 특정 속성 이름/값 쌍을 검색합니다. 모든 문서 속성은 검색할 수 있는 해당 관리 속성이 있는 SharePoint 있습니다. 예를 들어 SharePoint 사이트 모음은 **이름이 Customer인** 필수 필드와 함께 Trip Report라는 콘텐츠 형식을 사용할 **수 있습니다.** 사용자가 여행 보고서를 만드는 경우 고객 이름을 입력해야 합니다. 이 속성 이름/값 쌍은 DLP 정책에서도 사용할 수 있습니다. 예를 들어 **고객** 필드에 **Contoso가** 포함되어 있을 때 게스트의 문서 액세스를 차단하는 규칙이 필요한 경우

특정 레이블이 있는 콘텐츠에 DLP 정책을 Microsoft 365 여기에 있는 단계를 수행하면 안 됩니다. 대신 보존 레이블을 DLP 정책의 조건으로 사용하는 [방법을 배워야 합니다.](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)

## <a name="before-you-create-the-dlp-policy"></a>DLP 정책 만들기 전

DLP 정책에서 Windows Server FCI 속성 또는 기타 속성을 사용하려면 먼저 SharePoint 관리 센터에서 관리 속성을 만들어야 합니다. 그 이유는 다음과 있습니다.

예제

> [!NOTE]
> 조건을 사용하여 DLP 규칙을 만들 때 크롤링 속성 이름이 아닌 관리 속성 이름을 사용해야 `ContentPropertyContainsWords` 합니다.

이는 DLP가 검색 크롤러를 사용하여 사이트에서 중요한 정보를 식별하고 분류한 다음 해당 중요한 정보를 검색 인덱스의 보안 부분에 저장하기 때문에 중요합니다. Office 365로 문서를 업로드하는 경우 SharePoint는 문서 속성을 기준으로 크롤링된 속성을 자동으로 만듭니다. 그러나 FCI 또는 DLP 정책의 다른 속성을 사용하려면 해당 속성을 갖는 콘텐츠가 인덱스에 보관될 수 있게 크롤링된 속성이 관리 속성에 매핑되어야 합니다.

검색 및 관리 속성에 대한 자세한 내용은 [Manage the search schema in SharePoint Online를 참조하십시오.](/sharepoint/manage-search-schema)

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>1단계: 필요한 속성을 갖는 문서를 Office 365에 업로드합니다.

먼저 DLP 정책에서 참조하려는 속성을 갖는 문서를 업로드해야 합니다. Microsoft 365 속성이 검색되고 해당 속성에서 크롤링 속성이 자동으로 생성됩니다. 다음 단계에서는 관리 속성을 만든 다음 관리 속성을 이 크롤링 속성에 매핑합니다.

### <a name="step-2-create-a-managed-property"></a>2단계: 관리 속성 만들기

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에 로그인합니다.

2. 왼쪽 탐색 창에서 관리 센터 **를** \> **SharePoint.** 이제 사용자는 SharePoint 관리 센터에 있습니다.

3. 왼쪽 탐색에서 검색 관리 **페이지** 검색 Schema 관리 에서 \>  \> **검색을 선택합니다.**

   ![검색 관리 센터의 SharePoint 페이지입니다.](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. 관리 **속성 페이지에서** 새 \> **관리 속성 을 클릭합니다.**

   ![새 관리 속성 단추가 강조 표시된 관리 속성 페이지](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. 속성의 이름 및 설명을 입력합니다. 이 이름은 DLP 정책에 표시되는 이름입니다.

6. **형식** 에서 **텍스트** 를 선택합니다.

7. **기본 특징** 아래에서 **쿼리 가능** 및 **조회 가능** 을 선택합니다.

8. **크롤링 속성에 매핑에서** \> **매핑을 추가합니다.**

9. **크롤링** 속성 선택 대화 상자에서 Windows Server FCI 속성 또는 DLP 정책 확인에 사용할 기타 속성에 해당하는 크롤링 속성을 찾아 \> \> **선택합니다.**

   ![크롤링 속성 선택 대화 상자](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. 페이지 맨 아래에서 \> 확인을 **클릭합니다.**

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>FCI 속성 또는 기타 속성을 사용하는 DLP 정책 만들기

이 예에서 조직은 서버 기반 파일 서버에서 Windows FCI를 사용하고 있습니다. 특히, 높음, 보통, 낮음,  공용 및 PII가 아닌 값과 함께 개인 식별이 가능한 정보라는 FCI 분류 **속성을 사용합니다.**  이제 기존 FCI 분류를 기존 FCI 정책의 DLP 정책에 Office 365.

먼저 위 단계에 따라 SharePoint Online에서 관리 속성을 만듭니다. 이 속성은 FCI 속성에서 자동으로 만들어진 크롤링 속성에 매핑됩니다.

그런 다음 Document 속성에 다음 값 중 한 가지가 포함된 조건을 사용하는 두 규칙이 모두 포함된 DLP **정책을 생성합니다.**

- **FCI PII 콘텐츠 - 높음, 보통** 첫 번째 규칙은 FCI 분류 속성 개인  식별 정보가 **높음** 또는 보통인  경우 문서에 대한 액세스를 제한하고 문서가 조직 외부의 사용자와 공유되는 경우 해당 문서에 대한 액세스를 제한합니다.

- **FCI PII 콘텐츠 - 낮음** 두 번째 규칙은 FCI 분류 속성 개인 식별  정보가 낮음과 같고  문서가 조직 외부의 사용자와 공유되는 경우 문서 소유자에게 알림을 전송합니다.

### <a name="create-the-dlp-policy-by-using-powershell"></a>PowerShell을 사용하여 DLP 정책 만들기

문서 **속성에** 이러한 값이 포함된 조건은 보안 및 준수 센터의 UI에서 일시적으로 사용할 수 없지만 PowerShell을 사용하여 이 조건을 사용할 &amp; 수 있습니다. cmdlet을 사용하여 DLP 정책을 사용할 수 있으며 매개 변수와 `New\Set\Get-DlpCompliancePolicy` 함께 cmdlet을 사용하여 Document 속성에 이러한 값이 포함된 조건을 `New\Set\Get-DlpComplianceRule` 추가할 수 `ContentPropertyContainsWords` **있습니다.**

이러한 cmdlet에 대한 자세한 내용은 보안 및 준수 [ &amp; 센터 cmdlet을 참조하세요.](/powershell/exchange/exchange-online-powershell)

1. [커넥트 PowerShell을 사용하여 보안 및 준수 &amp; 센터에 연결](/powershell/exchange/connect-to-scc-powershell)

2. 를 사용하여 정책을  `New-DlpCompliancePolicy` 생성합니다.

이 PowerShell은 모든 위치에 적용되는 DLP 정책을 만듭니다.

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. 를 사용하여 위에서 설명한 두 규칙을 만들 수 있습니다. 여기서 한 규칙은 Low 값에 대해, 다른 규칙은 `New-DlpComplianceRule` **High** 및 **Moderate 값에 대한** 규칙입니다. 

   다음은 이러한 두 규칙을 만드는 PowerShell 예제입니다. 속성 이름/값 쌍은 따오기 표시로 묶고, 속성 이름은 공백이 없는 여러 값을 각기 0으로 구분하여 지정할 수 있습니다.  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Windows 서버 FCI에는 이 예에서 사용되는 개인 식별 정보를 비롯한 여러 기본 **제공** 속성이 포함되어 있습니다. 각 속성에 대해 가능한 값은 조직마다 다를 수 있습니다. 여기에 **사용된 High,** **Moderate** 및 **Low** 값은 예일 뿐입니다. 조직의 경우 Windows 서버 기반 파일 서버의 서버 리소스 관리자 파일에서 가능한 값으로 Windows 서버 FCI 분류 속성을 볼 수 있습니다. 자세한 내용은 분류 속성 [만들기를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759215(v=ws.11))

완료되면 정책에 문서 속성을 사용하는 두 개의 새 규칙에 이러한 값 **조건이 모두 포함되어야** 합니다. 다른 조건, 작업 및 설정이 나타나지만 이 조건은 UI에 나타나지 않습니다.

규칙 하나는 **개인 식별 정보** 속성이 **높은** 또는 **보통** 인 콘텐츠에 대한 액세스를 차단합니다. 또 다른 규칙은 **개인 식별 정보** 속성이 **낮음** 인 콘텐츠에 대해 알림을 보냅니다.

![방금 만든 두 개의 규칙을 보여 주며 새 DLP 정책 대화 상자입니다.](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>DLP 정책을 만든 후

이전 섹션의 단계를 수행하면 해당 속성이 있는 콘텐츠를 빠르게 검색하는 DLP 정책이 만들어지지만 해당 콘텐츠가 새로 업로드된 경우(콘텐츠가 인덱싱될 수 있도록) 또는 해당 콘텐츠가 오래 되지만 방금 편집된 콘텐츠인 경우(콘텐츠가 다시 인덱싱될 수 있도록) 하는 DLP 정책이 생성됩니다.

모든 위치에서 해당 속성을 갖는 콘텐츠를 검색하려는 경우 DLP 정책이 해당 속성의 모든 콘텐츠를 인식할 수 있게 라이브러리, 사이트 또는 사이트 모음을 다시 인덱싱하도록 수동으로 요청할 수 있습니다. SharePoint Online에서 콘텐츠는 정의된 크롤링 일정에 따라 자동으로 크롤링됩니다. 크롤러는 마지막 크롤링 이후에 변경된 콘텐츠를 선택하고 인덱스를 업데이트합니다. 예약된 다음 크롤링 전에 DLP 정책을 통해 콘텐츠를 보호해야 할 경우 다음 단계를 수행할 수 있습니다.

> [!CAUTION]
> 사이트를 다시 인덱싱하면 검색 시스템에서 대량의 부하가 발생할 수 있습니다. 시나리오에서 반드시 필요한 경우를 한 사이트를 다시 인덱싱하지 않습니다.

자세한 내용은 [사이트, 라이브러리 또는 목록을 크롤링 및 다시 인덱싱하도록 수동으로 요청](/sharepoint/crawl-site-content)을 참조하세요.

### <a name="reindex-a-site-optional"></a>사이트 다시 인덱스(선택 사항)

1. 사이트에서 설정(오른쪽 **위에** 있는 기어 아이콘) \> **사이트** 설정.

2. **검색에서** 검색 및 오프라인 **가용성** 다시 \> **인덱스 사이트를 선택 합니다.**

## <a name="more-information"></a>추가 정보

- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)

- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)

- [DLP 정책에 대한 알림을 보내고 정책 팁 표시](use-notifications-and-policy-tips.md)

- [DLP 정책 템플릿에 포함되는 내용](what-the-dlp-policy-templates-include.md)

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)