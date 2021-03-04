---
title: 고급 eDiscovery 사례로 수급자 가져오기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 가져오기 도구 d를 사용하여 Advanced eDiscovery의 사례에 여러 보호자 및 관련 데이터 원본을 빠르게 추가합니다.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421615"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>고급 eDiscovery 사례로 수급자 가져오기

많은 수의 관리인이 포함된 Advanced eDiscovery 사례의 경우 사례에 추가하는 데 필요한 정보가 포함된 CSV 파일을 사용하여 여러 관리인을 동시에 가져올 수 있습니다.

## <a name="import-custodians"></a>Custodians 가져오기

1. Advanced eDiscovery 사례를 열고 데이터 원본 **탭을** 선택합니다.

2. 데이터 **원본 추가를**  >  **클릭합니다. 보호자 가져오기 를 클릭합니다.**

3. 가져오기 **custodians** 플라이아웃  페이지에서 빈 템플릿 다운로드를 클릭하여 custodian template CSV 파일을 다운로드합니다.

   ![수장 가져오기 플라이아웃 페이지에서 CSV 템플릿 다운로드](../media/ImportCustodians1.png)

4. CSV 파일에 custodial 정보를 추가하고 로컬 컴퓨터에 저장합니다. CSV 파일의 필수 속성에 대한 자세한 내용은 [Custodian CSV](#custodian-csv-file) 파일 섹션을 참조하세요.

5. cstodian 정보를 사용하여 CSV 파일을 준비한 후 데이터  원본 탭으로 돌아가서 데이터 원본 추가를 다시  >   클릭합니다.

6. 보호자  가져오기 플라이아웃 페이지에서 찾아보기를 클릭한 다음, 보호자 정보가 포함된 CSV 파일을 업로드합니다. 

   CSV 파일을 업로드하면 **BulkAddCustodian이라는** 작업이 만들어지며 작업 **탭에** 표시됩니다. 이 작업은 보호자 및 관련 데이터 원본의 유효성을 검사한 다음 사례의 데이터 원본 페이지에 추가합니다. 

## <a name="custodian-csv-file"></a>Custodian CSV 파일

CSV custodian 템플릿을 다운로드한 후 각 행에 보호자 및 해당 데이터 원본을 추가할 수 있습니다. 머리줄 행의 열 이름은 변경하지 말아야 합니다. 작업 유형 및 작업 위치 열을 사용하여 다른 데이터 원본을 보호자에 연결합니다.

| 열 이름|설명|
|:------- |:------------------------------------------------------------|
|**Custodian contactEmail**     |Custodian의 UPN 전자 메일 주소입니다. 예를 들어 sarad@contoso.onmicrosoft.com.           |
|**Exchange 사용** | CUSTODian의 사서함을 포함하거나 포함하지 않을 TRUE/FALSE 값입니다.      |
|**OneDrive 사용** | 관리인의 비즈니스용 OneDrive 계정을 포함하거나 포함하지 않을 TRUE/FALSE 값입니다. |
|**Is OnHold**        | 보유자 데이터 원본을 보류할지 여부를 나타내는 TRUE/FALSE 값입니다. <sup>1</sup>     |
|**Workload1 유형**         |보호자에 연결되는 데이터 원본의 유형을 나타내는 문자열 값입니다. 가능한 값은 다음과 같습니다. <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Workload1 Location**     | 작업 유형에 따라 데이터 원본의 위치가 됩니다. 예를 들어 Exchange 사서함의 전자 메일 주소 또는 SharePoint 사이트의 URL을 예로 들 수 있습니다. |
|||

> [!NOTE]
> <sup>1</sup> 보유자 가져오기 프로세스 및 CSV 파일을 사용하여 최대 1,000개 사서함과 100개 사이트를 보류할 수 있습니다. 이 프로세스를 사용하여 사례에 1,000명 이상의 보유자 추가를 할 수 있지만 보류 제한은 계속 적용됩니다. 보류 제한에 대한 자세한 내용은 [Limits in Advanced eDiscovery을 참조하십시오.](limits-ediscovery20.md#hold-limits)

다음은 보호자 정보가 있는 CSV 파일의 예입니다.<br/><br/>

|Custodian contactEmail      | Exchange 사용 | OneDrive 사용 | Is OnHold | Workload1 유형 | Workload1 Location             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>보호자 및 데이터 원본 유효성 검사

보안 CSV 파일을 업로드한 후 Advanced eDiscovery는 다음을 합니다.

1. 보호자 및 데이터 원본의 유효성을 검사합니다.

2. 각 보유자에 대한 모든 데이터 원본을 인덱싱하고 보류합니다(CSV 파일의 **Is OnHold** 속성이 TRUE로 설정된 경우).

### <a name="custodian-validation"></a>Custodian validation

현재는 조직의 Azure AD(Azure Active Directory)에 포함된 관리인만 가져올 수 있습니다.

custodian 가져오기 도구는 CSV 파일의 **Custodian contactEmail** 열에 있는 UPN 값을 사용하여 관리인을 찾고 유효성을 검사합니다. 유효성이 검사된 보호자는 사례에 자동으로 추가되고 사례의 데이터 원본 **탭에** 나열됩니다. 보직의 유효성을 검사할 수 없는 경우 해당 사례의 작업 탭에 나열된 BulkAddCustodian  작업의 오류 로그에 나열됩니다. 미확인된 보호자는 사례에 추가되거나 데이터 원본 탭에 **나열되지** 않습니다.

### <a name="data-source-validation"></a>데이터 원본 유효성 검사

관리인이 유효성을 검사하고 사례에 추가된 후, 관리인과 연결된 각 기본 사서함 및 OneDrive 계정이 추가됩니다.

그러나 관리인과 연결된 다른 데이터 원본(예: SharePoint 사이트, Microsoft Teams, Microsoft 365 그룹 또는 Yammer 그룹)을 찾을 수 없는 경우 어느 것도 관리인에게 할당되지 않은 것이고 유효성  검사되지 않은 값은 데이터 원본  탭의 관리자 옆에 있는 상태 열에 표시됩니다. 

보호자에 대해 유효성이 검사된 데이터 원본을 추가하는 경우:

1. 데이터 원본 **탭에서** 유효성이 검사되지 않은 데이터 원본이 포함된 보호기를 선택합니다.

2. 보호자 플라이아웃 페이지에서 **Custodial 위치** 섹션으로 스크롤하여 보호자와 연결된 유효성이 검사된 데이터 원본과 미확인 데이터 원본을 모두 니다.

3. **플라이아웃** 페이지 위쪽에서 편집을 클릭하여 잘못된 데이터 원본을 제거하거나 새 데이터 원본을 추가합니다.

4. 미확인 데이터 원본을 제거하거나 새 데이터 원본을 추가하면  **데이터** 원본 탭의 보위원에 대한 상태 열에 Active 값이 **표시됩니다.** 이전에 유효하지 않은 것으로 나타난 원본을 추가하려면 아래 수정 단계에 따라 관리인에게 수동으로 추가합니다.

### <a name="remediating-invalid-data-sources"></a>잘못된 데이터 원본 수정

이전에 유효하지 않은 데이터 원본을 수동으로 추가하고 연결하려면

1. 데이터 원본 **탭에서** 이전에 유효하지 않은 데이터 원본을 수동으로 추가하고 연결하기 위해 보호 기능을 선택합니다.

2. **플라이아웃** 페이지 위쪽에서 편집을 클릭하여 사서함, 사이트, Teams 또는 Yammer 그룹을 관리인과 연결합니다. 해당 데이터 위치 유형 옆에 있는 **편집을** 클릭하여 이 작업을 합니다.

3. 다음을 클릭하여 보류 설정 페이지를 **표시하고** 추가한 데이터 원본에 대한 보류 설정을 구성합니다. 

4. **다음을** 클릭하여 보호자 검토 **페이지를** 표시한 다음  제출을 클릭하여 변경 내용을 저장합니다.
