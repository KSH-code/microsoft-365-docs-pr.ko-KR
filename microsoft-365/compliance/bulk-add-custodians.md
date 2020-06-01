---
title: 고급 eDiscovery 사례에 custodians 대량 추가
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432441"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a>대량-Advanced eDiscovery 사례 (미리 보기)에 custodians 추가

많은 수의 custodians 포함 된 고급 eDiscovery 사례의 경우 여러 custodians를 사례에 추가 하는 데 필요한 모든 정보를 포함 하는 CSV 파일을 한 번에 가져올 수도 있습니다.

## <a name="bulk-add-custodians"></a>대량 추가 custodians

1. 사례를 입력 하 고 **원본** 탭으로 이동 합니다.

2. **가져오기 custodians** 를 클릭 합니다.

3. 플라이 아웃 페이지에서 **빈 서식 파일 다운로드** 를 클릭 하 여 CSV custodian 서식 파일을 다운로드 합니다.

4. CSV 파일에 custodial 정보를 추가 하 고 로컬 컴퓨터에 저장 합니다. CSV 파일의 속성에 대 한 자세한 내용은 다음 섹션을 참조 하십시오.

5. **원본** 탭에서 **Custodians 가져오기를** 다시 클릭 합니다. 
6. 플라이 아웃 페이지에서 **찾아보기를** 클릭 하 고 CSV 파일을 업로드 합니다.

   CSV 파일이 업로드 된 후에는 BulkAddCustodian 작업이 만들어지고 **작업** 탭에 표시 됩니다. 이 작업은 custodians의 해당 하는 데이터 원본에 대 한 유효성을 검사 한 다음 케이스의 **원본** 페이지에 있는 **custodians** 탭에 추가 합니다.

## <a name="custodian-csv-file"></a>Custodian CSV 파일

CSV 서식 파일을 다운로드 한 후에는 각 행에 custodians 및 해당 데이터 원본을 추가할 수 있습니다. 머리글 행의 열 이름은 변경 하지 않도록 합니다.

| 열 이름|설명|
|:------- |:------------------------------------------------------------|
|**Custodian ContactEmail**     | Custodian의 UPN 전자 메일입니다. 예: sarad@onmicrosoft.contoso.com           |
|**Exchange 사용** | Custodian의 사서함을 추가할지 여부에 대 한 TRUE/FALSE 값입니다.      |
|**OneDrive 사용** | Custodian의 비즈니스용 OneDrive 계정을 추가할지 여부에 대 한 TRUE/FALSE 값입니다. |
|**OnHold**        | Custodian을 보류할 지 여부에 해당 하는 TRUE/FALSE 값입니다.       |
|**Workload1 형식**         | Custodian와 연결할 데이터 원본의 형식을 나타내는 문자열 값입니다. <br />가능한 값은 다음과 같습니다. <br />ExchangeMailbox, SharePointSite, TeamsMailbox, Teamsmailbox, YammerMailbox, YammerSite |
|**Workload1 위치**     | 작업 유형에 따라 작업의 데이터 위치 (예: Exchange 사서함의 전자 메일 주소 또는 SharePoint 사이트의 URL)가 여기에 해당 합니다. |
|||

다음은 custodian 정보를 포함 하는 CSV 파일의 예입니다.  

| ContactEmail      | Exchange 사용 | OneDrive 사용 | OnHold | Workload1 형식 | Workload1 위치             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|sarad@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Custodian 및 데이터 원본 유효성 검사

Custodian CSV 파일을 업로드 하는 경우 Advanced eDiscovery는 다음 작업을 수행 합니다.

1. Custodians 및 해당 데이터 원본의 유효성을 검사 합니다. 

2. 각 custodian에 대 한 모든 데이터 원본을 인덱싱하고이를 보류 합니다 (OnHold property가 TRUE로 설정 된 경우).

### <a name="custodian-validation"></a>Custodian 유효성 검사

현재는 AAD (Azure Active Directory)에 있는 custodians 가져오기를 지원 합니다.

CSV 파일의 **담당자 전자 메일** 열에서 UPN 값을 사용 하 여 custodians를 확인 하 고 확인 합니다. 유효성이 검사 된 Custodians 사례에 자동으로 추가 되 고 케이스의 **원본** 페이지에 있는 **Custodian** 탭에 나열 됩니다. Custodian의 유효성을 검사할 수 없는 경우 서비스 케이스의 **작업** 탭에 나열 된 BulkAddCustodian 작업에 대 한 오류 로그에 나열 됩니다. Unvalidated custodians가 사례에 추가 되지 않습니다.

### <a name="data-source-validation"></a>데이터 원본 유효성 검사

Custodians가 유효성을 검사 하 고 사례에 추가 된 후에는 custodian와 연결 된 각 데이터 원본의 유효성이 검사 됩니다. Custodian에 대 한 데이터 원본을 찾을 수 없는 경우 **유효성을 검사 하지 않은** 값은 해당 Custodian의 **custodian** 탭에 있는 **유효성이 검사** 된 열에 표시 됩니다.

### <a name="remediating-unvalidated-data-sources"></a>수정 unvalidated 데이터 원본

Unvalidated 데이터 원본을 사용 하 여 custodians을 재구성 하려면: 

1. **Custodian** 탭에서 유효성이 검사 되지 않은 Custodian을 선택 합니다.

2. Custodian 플라이 아웃 페이지에서 **데이터 원본** 섹션으로 스크롤하여 custodian에 연결 된 데이터 원본을 확인 합니다. 유효성이 검사 되 고 unvalidated 데이터 원본이 모두 나열 됩니다.

3. **데이터 원본** 섹션에서 **편집**을 클릭 합니다.

4. **Custodial 위치 선택** 페이지에서 unvalidated 데이터 원본을 제거 합니다.

5. **추가 위치 선택** 페이지에서 **업데이트** 를 클릭 하 여 custodian에 대 한 데이터 원본을 더 추가 합니다.
