---
title: 콘텐츠 탐색기 시작하기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 콘텐츠 탐색기를 사용하여 레이블이 지정된 항목을 원래 상태로 볼 수 있습니다.
ms.openlocfilehash: e1cae053c7b13ceec9c7f3274122cf004c7277e5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184196"
---
# <a name="get-started-with-content-explorer"></a>콘텐츠 탐색기 시작하기

데이터 분류 콘텐츠 탐색기를 사용하여 개요 페이지에 요약된 항목을 원래 상태로 볼 수 있습니다.

![콘텐츠 탐색기 축소 스크린샷.](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a>필수 구성 요소

테이터 분류에 액세스하고 이를 사용하는 모든 계정에는 다음 구독 중 하나에서 할당된 라이선스가 있어야 합니다.

- Microsoft 365 (E5)
- Office 365 (E5)
- 고급 규정 준수 (E5) 추가 기능
- 고급 위협 인텔리전스 (E5) 추가 기능
- Microsoft 365 E5/A5 정보 보호 및 거버넌스
- Microsoft 365 E5/A5 규정 준수


### <a name="permissions"></a>권한

콘텐츠 탐색기 탭에 액세스하려면 계정에 다음 역할이나 역할 그룹 중 하나의 구성원 자격이 할당되어야 합니다. 

**Microsoft 365 역할 그룹**

- 전역 관리자
- 준수 관리자
- 보안 관리자
- 규정 준수 데이터 관리자

> [!IMPORTANT]
> 이러한 역할 그룹의 구성원은 콘텐츠 탐색기의 항목 목록을 보거나 콘텐츠 탐색기의 항목 내용을 볼 수 없습니다.

> [!IMPORTANT]
> 전역 관리자만 준수 센터의 다른 사용자에게 권한을 관리하거나 할당할 수 있습니다. 자세한 내용은 [사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.
> 
### <a name="required-permissions-to-access-items-in-content-explorer"></a>콘텐츠 탐색기에서 항목에 액세스하는 데 필요한 권한

콘텐츠 탐색기에 대한 액세스는 검사된 파일의 내용을 읽을 수 있기 때문에 매우 제한적입니다.

> [!IMPORTANT]
> 이러한 권한은 해당 항목에 로컬로 할당되는 권한을 대체하여 콘텐츠를 볼 수 있게 합니다. 

콘텐츠 탐색기에는 액세스 권한을 부여하는 두 가지 역할이 있으며 [규정 준수 센터](https://compliance.microsoft.com/permissions)를 사용하여 부여됩니다.

- **콘텐츠 탐색기 목록 뷰어**: 이 역할 그룹의 구성원 자격으로 목록 보기에서 각 항목과 해당 위치를 볼 수 있습니다. `data classification list viewer` 역할이 사전에 이 역할 그룹에 할당되었습니다.

- **콘텐츠 탐색기 콘텐츠 뷰어**:이 역할 그룹의 멤버 자격으로 목록에 있는 각 항목의 내용을 볼 수 있습니다. `data classification content viewer` 역할이 사전에 이 역할 그룹에 할당되었습니다.

콘텐츠 탐색기에 액세스하는 데 사용하는 계정은 역할 그룹 중 하나 또는 둘 다에 있어야 합니다. 이러한 역할은 독립적인 역할 그룹이며 누적되지 않습니다. 예를 들어 계정에 항목 및 해당 위치만 볼 수 있는 권한을 부여 하려는 경우 콘텐츠 탐색기 목록 표시기 권한을 부여 합니다. 동일한 계정에서 목록에 있는 항목의 내용을 볼 수 있게 하려면 콘텐츠 탐색기 콘텐츠 뷰어 권한도 부여합니다.

사용자 지정 역할 그룹에 역할 중 하나 또는 둘 다를 할당하여 콘텐츠 탐색기에 대한 액세스를 조정할 수도 있습니다.

전역 관리자, 준수 관리자 또는 데이터 관리자는 필요한 콘텐츠 탐색기 목록 뷰어와 콘텐츠 탐색기 콘텐츠 뷰어 역할 그룹 구성원 자격을 할당할 수 있습니다.

## <a name="content-explorer"></a>콘텐츠 탐색기

콘텐츠 탐색기는 민감도 레이블, 보존 레이블이 있거나, 조직에서 중요한 정보 유형으로 분류된 항목의 현재 스냅샷을 표시합니다.

### <a name="sensitive-information-types"></a>중요한 정보 유형

[DLP 정책](dlp-learn-about-dlp.md)은 **중요한 정보 유형** 으로 정의되어 있는 중요한 정보를 보호하는 데 도움을 줄 수 있습니다. Microsoft 365는 사용자가 사용할 수 있는 많은 지역에서 [흔한 중요한 정보 유형에 대한 정의](sensitive-information-type-entity-definitions.md)를 포함합니다. 예를 들면 신용 카드 번호, 은행 계좌 번호, 국가 ID 번호 그리고 Windows Live ID 서비스 번호 등이 있습니다.

> [!NOTE]
> 현재 콘텐츠 탐색기에서는 Exchange Online의 중요한 정보 유형을 검사하지 않습니다.

### <a name="sensitivity-labels"></a>민감도 레이블

[민감도 레이블](sensitivity-labels.md)은 단순히 조직에 항목의 값을 나타내는 태그입니다. 이는 수동으로 또는 자동으로 적용될 수 있습니다. 적용한 후에는 문서에 포함이 되고 문서가 이동하는 곳마다 따르게 됩니다. 민감도 레이블은 필수 워터마크 또는 암호화와 같은 다양한 보호 작용을 가능하도록 해줍니다.

데이터 분류 페이지에서 해당 데이터를 표시하려면 SharePoint 및 OneDrive에 있는 파일에 민감도 레이블을 사용하도록 설정되어 있어야 합니다. 자세한 내용은 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md)을 참조하세요.

### <a name="retention-labels"></a>보존 레이블

[보존 레이블](retention.md)을 사용하여 레이블이 부착된 항목이 보관되는 기간 및 삭제하기 전에 수행해야 할 단계를 정의할 수 있습니다. 이들은 수동으로 또는 자동으로 정책을 통해 적용됩니다. 이들은 조직이 법적 그리고 규제적 요구 사항을 계속 준수하는데 도움이 되는 역할을 할 수 있습니다.

### <a name="how-to-use-content-explorer"></a>콘텐츠 탐색기를 사용하는 방법

1. **Microsoft 365 준수 센터**  > **데이터 분류** > **콘텐츠 탐색기**
2. 레이블 이름 또는 중요한 정보 유형을 알고 있는 경우 필터 상자에 입력할 수 있습니다.
3. 또는 레이블 유형을 확장하고 목록에서 레이블을 선택하여 항목을 찾아볼 수 있습니다.
4. **모든 위치** 에서 위치를 선택하고 폴더 구조를 드릴다운하여 해당 항목까지 이동합니다.
5. 콘텐츠 탐색기에서 기본적으로 항목을 열려면 두 번 클릭을 합니다.

### <a name="export"></a>내보내기
**내보내기** 컨트롤은 **모든 위치** 창에 표시되는 모든 항목의 목록을 포함하는 .csv 파일을 만듭니다.

![데이터 분류 내보내기 관리.](../media/data_classification_export_control.png)


### <a name="search"></a>검색

Exchange 폴더나 SharePoint 또는 OneDrive 사이트와 같은 위치로 드릴다운하면 **검색** 도구가 나타납니다.

![콘텐츠 탐색기 검색 도구.](../media/data_classification_search_tool.png)


검색 도구의 범위는 **모든 위치** 창에 표시되는 내용이며 검색 가능한 항목은 선택한 위치에 따라 다릅니다. 

**Exchange** 가 선택된 위치인 경우 사서함의 전체 전자 메일 주소(예: `user@domainname.com`)를 검색할 수 있습니다.

**SharePoint** 또는 **OneDrive** 가 선택된 위치인 경우 사이트 이름, 폴더 및 파일로 드릴다운하면 검색 도구가 표시됩니다. 

> [!NOTE]
> **OneDrive** 미리 보기 프로그램 동안 OneDrive 통합에 대한 유용한 피드백을 잘 들었습니다. 해당 피드백에 따라 OneDrive 기능은 모든 수정 내용이 적용될 때까지 미리 보기에 유지됩니다. 테넌트에 따라 일부 고객의 경우 OneDrive를 위치로 보지 못할 수 있습니다. 이에 대한 귀하의 지속적인 지원에 감사드립니다.

다음을 검색할 수 있습니다.


|값|예  |
|---------|---------|
|전체 사이트 이름    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|루트 폴더 이름 - 모든 하위 폴더를 가져옵니다.    | `/sites`        |
|파일 이름    |    `RES_Resume_1234.txt`     |
|파일 이름 시작 부분에 있는 텍스트| `RES`|
|파일 이름에서 밑줄 문자(_) 다음에 오는 텍스트|`Resume` 또는 `1234`| 
|파일 확장명|`txt`|


## <a name="see-also"></a>참고 항목

- [민감도 레이블에 대해 알아보기](sensitivity-labels.md)
- [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)
- [중요한 정보 유형 엔터티 정의.md](sensitive-information-type-entity-definitions.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
