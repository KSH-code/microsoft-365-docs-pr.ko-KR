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
description: DLP (데이터 손실 방지) 정책을 사용 하 여 타사 시스템의 속성이 포함 된 문서를 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: a3dd82dae76336dc3d1293430e10ba505585e707
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562979"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기

Microsoft 365 DLP (데이터 손실 방지) 정책은 분류 속성 또는 항목 속성을 사용 하 여 중요 한 항목을 식별할 수 있습니다. 예를 들면 다음을 사용할 수 있습니다.

- Windows Server FCI (파일 분류 인프라) 속성
- SharePoint 문서 속성
- 타사 시스템 문서 속성

![Office 365 외부 분류 시스템을 보여 주는 다이어그램](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

예를 들어 조직에서 Windows Server FCI를 사용 하 여 주민 등록 번호와 같은 개인 데이터를 갖는 항목을 식별 한 다음, 개인 식별이 **가능한 정보** 속성을 문서에 있는 개인 데이터의 유형 및 수에 따라 **고급**, **보통**, **낮음**, **공용** 또는 **PII가 아닌** 사용자로 분류 하 여 문서를 분류할 수 있습니다.

Microsoft 365에서는 해당 속성이 **High** 및 **Medium** 과 같은 특정 값으로 설정 된 문서를 식별 하는 DLP 정책을 만든 다음 해당 파일에 대 한 액세스를 차단 하는 등의 작업을 수행할 수 있습니다. 해당 속성이 **낮음** 으로 설정된 경우에는 전자 메일 알림 전송 등의 다른 작업을 수행하는 다른 규칙을 동일한 정책에 만들 수도 있습니다. 이러한 방식으로 DLP는 Windows Server FCI와 통합 되며, Windows Server 기반 파일 서버에서 Microsoft 365로 업로드 되거나 공유 되는 Office 문서를 보호 하는 데 도움이 될 수 있습니다.

DLP 정책은 단순히 특정 속성 이름/값 쌍을 찾습니다. 속성에 SharePoint search에 해당 하는 관리 속성이 있으면 모든 문서 속성을 사용할 수 있습니다. 예를 들어 SharePoint 사이트 모음에는 **Customer** 라는 필수 필드와 함께 **트립 보고서** 라는 콘텐츠 형식이 사용 될 수 있습니다. 사용자가 출장 보고서를 만들 때마다 고객 이름을 입력 해야 합니다. 이 속성 이름/값 쌍은 DLP 정책 에서도 사용할 수 있으며, 예를 들어 **Customer** 필드에 **Contoso** 가 포함 되어 있는 경우 게스트가 문서에 대 한 액세스를 차단 하는 규칙을 원하는 경우입니다.

특정 Microsoft 365 레이블이 있는 콘텐츠에 DLP 정책을 적용 하려면 여기에 나와 있는 단계를 수행 하지 않는 것이 좋습니다. 대신 [보존 레이블을 DLP 정책의 조건으로 사용](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)하는 방법에 대해 알아보세요.

## <a name="before-you-create-the-dlp-policy"></a>DLP 정책 만들기 전

DLP 정책에서 Windows Server FCI 속성 또는 기타 속성을 사용하려면 먼저 SharePoint 관리 센터에서 관리 속성을 만들어야 합니다. 그 이유는 다음과 같습니다.

예제

DLP는 검색 크롤러를 사용 하 여 사이트에서 중요 한 정보를 식별 하 고 분류 한 다음 중요 한 정보를 검색 인덱스의 안전한 부분에 저장 하는 것이 중요 합니다. Office 365로 문서를 업로드하는 경우 SharePoint는 문서 속성을 기준으로 크롤링된 속성을 자동으로 만듭니다. 그러나 FCI 또는 DLP 정책의 다른 속성을 사용하려면 해당 속성을 갖는 콘텐츠가 인덱스에 보관될 수 있게 크롤링된 속성이 관리 속성에 매핑되어야 합니다.

검색 및 관리 속성에 대 한 자세한 내용은 [SharePoint Online에서 검색 스키마 관리](https://go.microsoft.com/fwlink/p/?LinkID=627454)를 참조 하세요.

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>1단계: 필요한 속성을 갖는 문서를 Office 365에 업로드합니다.

먼저 DLP 정책에서 참조하려는 속성을 갖는 문서를 업로드해야 합니다. Microsoft 365에서 속성을 검색 하 고 크롤링 속성을 자동으로 만듭니다. 다음 단계에서는 관리 속성을 만든 다음 관리 속성을이 크롤링 속성에 매핑합니다.

### <a name="step-2-create-a-managed-property"></a>2단계: 관리 속성 만들기

1. Microsoft 365 관리 센터에 로그인합니다.

2. 왼쪽 탐색 영역에서 **관리 센터** \> **SharePoint** 를 선택 합니다. 이제 사용자는 SharePoint 관리 센터에 있습니다.

3. 왼쪽 탐색 창의 검색 관리 페이지 **에서 검색** \> **search administration** \> **스키마 관리** 를 선택 합니다.

   ![검색 관리 페이지의 SharePoint 관리 센터](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. **관리 속성** 페이지에서 \> **새 관리 속성** 을 설정 합니다.

   ![관리 속성 페이지에서 새 관리 속성 단추가 강조 표시 된](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. 속성의 이름 및 설명을 입력합니다. 이 이름은 DLP 정책에 표시되는 이름입니다.

6. **형식** 에서 **텍스트** 를 선택합니다.

7. **기본 특징** 아래에서 **쿼리 가능** 및 **조회 가능** 을 선택합니다.

8. **크롤링 속성에** 매핑 아래에서 \> **매핑을 추가** 합니다.

9. **크롤링 속성 선택** 대화 상자에서 \> DLP 정책 확인에 사용할 Windows Server fci 속성 또는 기타 속성에 해당 하는 크롤링 속성을 찾아 선택 합니다 \> **OK**.

   ![크롤링된 속성 선택](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. 페이지 맨 아래에서 \> **확인을** 선택 합니다.

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>FCI 속성 또는 기타 속성을 사용하는 DLP 정책 만들기

이 예에서는 조직에서 Windows Server 기반 파일 서버에 FCI를 사용 하 고 있습니다. 특히 **높은**, **중간**, **낮음**, **공용**, **PII가 아닌** 사용할 수 있는 **개인 식별** 이 가능한 값이 포함 된 fci 분류 속성을 사용 하 고 있습니다. 이제 Office 365에서 해당 DLP 정책에 기존 FCI 분류를 사용 하려고 합니다.

먼저 위 단계에 따라 SharePoint Online에서 관리 속성을 만듭니다. 이 속성은 FCI 속성에서 자동으로 만들어진 크롤링 속성에 매핑됩니다.

다음으로, 조건 **문서 속성** 을 사용 하는 두 개의 규칙을 포함 하는 DLP 정책을 만듭니다.

- **Fci PII 콘텐츠-높음, 보통** 첫 번째 규칙은 FCI 분류 속성 **개인 식별 정보가** **높은** 또는 **보통** 이 고 문서가 조직 외부의 사용자와 공유 되는 경우 문서에 대 한 액세스를 제한 합니다.

- **Fci PII 콘텐츠-낮음** 두 번째 규칙은 FCI 분류 속성 **개인 식별 정보가** **낮은** 정보이 고 문서가 조직 외부의 사용자와 공유 되는 경우 문서 소유자에 게 알림을 보냅니다.

### <a name="create-the-dlp-policy-by-using-powershell"></a>PowerShell을 사용 하 여 DLP 정책 만들기

조건 **문서 속성에 포함 된 이러한 값** 은 일시적으로 보안 및 준수 센터의 UI에서 사용할 수 &amp; 없지만 PowerShell을 사용 하 여이 조건을 계속 사용할 수 있습니다. Cmdlet을 사용  `New\Set\Get-DlpCompliancePolicy` 하 여 DLP 정책에 대 한 작업을 수행 하 고  `New\Set\Get-DlpComplianceRule` 매개 변수와 함께 cmdlet을 사용  `ContentPropertyContainsWords` 하 여 조건을 추가할 수 있습니다 **문서 속성에 이러한 값이 포함 되어** 있습니다.

이러한 cmdlet에 대 한 자세한 내용은 [Security &amp; 준수 센터 cmdlet](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)를 참조 하세요.

1. [&amp;원격 PowerShell을 사용 하 여 보안 및 준수 센터에 연결](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. 을 사용 하 여 정책을 만듭니다  `New-DlpCompliancePolicy` .

이 PowerShell은 모든 위치에 적용 되는 DLP 정책을 만듭니다.

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. 위에서 설명한 두 가지 규칙을 사용 하 여  `New-DlpComplianceRule` , 즉 **낮은** 값에 대 한 규칙을 만들고, **높은** 값과 **중간** 가치에 대해 다른 규칙을 만듭니다.

   다음은 이러한 두 가지 규칙을 만드는 PowerShell 예제입니다. 속성 이름/값 쌍은 큰따옴표로 묶여 있고 속성 이름에는 공백 없이 쉼표로 구분 된 여러 값을 다음과 같이 지정할 수 있습니다.  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Windows Server FCI에는이 예에서 사용 되는 **개인 식별** 이 가능한 정보를 포함 하 여 기본 제공 되는 여러 속성이 포함 되어 있습니다. 각 속성에 사용할 수 있는 값은 조직 마다 다를 수 있습니다. 여기에서 사용 되는 **높은** 값, **중간 규모** 및 **낮음을** 예로 들 수 있습니다. 조직의 경우 Windows server FCI 분류 속성을 사용할 수 있는 값을 포함 하는 파일 서버 기반 파일 서버 자세한 내용은 [분류 속성 만들기](https://go.microsoft.com/fwlink/p/?LinkID=627456)항목을 참조 하십시오.

완료 되 면 정책에는 문서 속성을 사용 하는 두 가지 새 규칙에 **이러한 값 조건이 포함** 되어 있어야 합니다. 이 조건은 UI에는 표시 되지 않지만 다른 조건, 작업 및 설정은 표시 됩니다.

규칙 하나는 **개인 식별 정보** 속성이 **높은** 또는 **보통** 인 콘텐츠에 대한 액세스를 차단합니다. 또 다른 규칙은 **개인 식별 정보** 속성이 **낮음** 인 콘텐츠에 대해 알림을 보냅니다.

![방금 만든 두 규칙을 보여 주는 새로운 DLP 정책 대화](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>DLP 정책을 만든 후

이전 섹션의 단계를 수행 하면 해당 속성을 사용 하 여 콘텐츠를 빠르게 검색할 DLP 정책이 생성 되지만 콘텐츠가 새로 업로드 되는 경우 (콘텐츠가 인덱싱되지 않도록), 해당 콘텐츠가 이전에 편집 된 경우에만 콘텐츠가 다시 인덱싱되는 것을 확인할 수 있습니다.

모든 위치에서 해당 속성을 갖는 콘텐츠를 검색하려는 경우 DLP 정책이 해당 속성의 모든 콘텐츠를 인식할 수 있게 라이브러리, 사이트 또는 사이트 모음을 다시 인덱싱하도록 수동으로 요청할 수 있습니다. SharePoint Online에서 콘텐츠는 정의된 크롤링 일정에 따라 자동으로 크롤링됩니다. 크롤러는 마지막 크롤링 이후에 변경된 콘텐츠를 선택하고 인덱스를 업데이트합니다. 예약된 다음 크롤링 전에 DLP 정책을 통해 콘텐츠를 보호해야 할 경우 다음 단계를 수행할 수 있습니다.

> [!CAUTION]
> 사이트를 다시 인덱싱하면 검색 시스템에서 대량의 부하가 발생할 수 있습니다. 시나리오에서 절대적으로 필요한 경우가 아니면 사이트를 다시 인덱싱하지 마세요.

자세한 내용은 [사이트, 라이브러리 또는 목록을 크롤링 및 다시 인덱싱하도록 수동으로 요청](https://go.microsoft.com/fwlink/p/?LinkID=627457)을 참조하세요.

### <a name="reindex-a-site-optional"></a>사이트 다시 인덱싱 (선택 사항)

1. 사이트에서 **설정** (오른쪽 위의 기어 아이콘) \> **사이트 설정을** 선택 합니다.

2. **검색** 에서 **검색 및 오프 라인 가용성 다시** \> **인덱싱 사이트** 를 선택 합니다.

## <a name="more-information"></a>추가 정보

- [데이터 손실 방지 정책 개요](data-loss-prevention-policies.md)

- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)

- [DLP 정책에 대한 알림을 보내고 정책 팁 표시](use-notifications-and-policy-tips.md)

- [DLP 정책 템플릿에 포함되는 내용](what-the-dlp-policy-templates-include.md)

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
