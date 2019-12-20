---
title: 데이터 분류 콘텐츠 탐색기(미리 보기) 사용
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
search.appverid:
- MOE150
- MET150
description: 콘텐츠 탐색기를 사용하여 레이블이 지정된 항목을 원래 상태로 볼 수 있습니다.
ms.openlocfilehash: 8a795e0582599dc3160f896a6361b773caa6c4e4
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823800"
---
# <a name="using-data-classification-content-explorer-preview"></a>데이터 분류 콘텐츠 탐색기(미리 보기) 사용

데이터 분류 콘텐츠 탐색기를 사용하여 개요 페이지에 요약된 항목을 원래 상태로 볼 수 있습니다.

## <a name="content-explorer"></a>콘텐츠 탐색기

콘텐츠 탐색기는 민감도 레이블, 보존 레이블이 있거나, 조직에서 중요한 정보 유형으로 분류된 항목의 현재 스냅샷을 표시합니다.

### <a name="sensitive-information-types"></a>중요한 정보 유형

[DLP 정책](data-loss-prevention-policies.md)은 **중요한 정보 유형**으로 정의되어 있는 중요한 정보를 보호하는 데 도움을 줄 수 있습니다. Microsoft 365는 사용자가 사용할 수 있는 많은 지역에서 [흔한 중요한 정보 유형에 대한 정의](what-the-sensitive-information-types-look-for.md)를 포함합니다. 예를 들면 신용 카드 번호, 은행 계좌 번호, 국가 ID 번호 그리고 Windows Live ID 서비스 번호 등이 있습니다.

### <a name="sensitivity-labels"></a>민감도 레이블

[민감도 레이블](sensitivity-labels.md)은 단순히 조직에 항목의 값을 나타내는 태그입니다. 이는 수동으로 또는 자동으로 적용될 수 있습니다. 적용한 후에는 문서에 포함이 되고 문서가 이동하는 곳마다 따르게 됩니다. 민감도 레이블은 필수 워터마크 또는 암호화와 같은 다양한 보호 작용을 가능하도록 해줍니다. 엔드포인트 보호를 사용하도록 설정한 경우 항목이 조직의 컨트롤을 벗어나지 않도록 방지할 수도 있습니다.

데이터 분류 페이지에서 해당 데이터를 표시하려면 SharePoint 및 OneDrive에 있는 파일에 민감도 레이블을 사용하도록 설정되어 있어야 합니다. 자세한 내용은 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)](sensitivity-labels-sharepoint-onedrive-files.md)을 참조하세요.

### <a name="retention-labels"></a>보존 레이블

[보존 레이블](labels.md)을 사용하여 레이블이 부착된 항목이 보관되는 기간 및 삭제하기 전에 수행해야 할 단계를 정의할 수 있습니다. 이들은 수동으로 또는 자동으로 정책을 통해 적용됩니다. 이들은 조직이 법적 그리고 규제적 요구 사항을 계속 준수하는데 도움이 되는 역할을 할 수 있습니다.

![콘텐츠 탐색기 축소 스크린샷](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>사용 권한

콘텐츠 탐색기에 대한 액세스 권한을 부여하는 두 개의 역할이 있습니다.

- **콘텐츠 탐색기 목록 뷰어**: 이 역할의 멤버 자격으로 각 항목과 해당 위치를 볼 수 있습니다.

- **콘텐츠 탐색기 콘텐츠 뷰어**:이 역할의 멤버 자격으로 목록에 있는 각 항목의 내용을 볼 수 있습니다.

콘텐츠 탐색기에 액세스하는 데 사용하는 계정은 역할 중 하나 또는 둘 다에 있어야 합니다. 이러한 역할은 독립적인 역할이며 누적되지 않습니다. 예를 들어 계정에 항목 및 해당 위치만 볼 수 있는 권한을 부여 하려는 경우 콘텐츠 탐색기 목록 표시기 권한을 부여 합니다. 동일한 계정에서 목록에 있는 항목의 내용을 볼 수 있게 하려면 콘텐츠 탐색기 콘텐츠 뷰어 권한도 부여합니다.

### <a name="how-to-use-content-explorer"></a>콘텐츠 탐색기를 사용하는 방법

1. **Microsoft 365 준수 센터**  > **데이터 분류** > **콘텐츠 탐색기**
2. 레이블 이름 또는 중요한 정보 유형을 알고 있는 경우 검색 상자에 입력할 수 있습니다.
3. 또는 레이블 유형을 확장하고 목록에서 레이블을 선택하여 항목을 찾아볼 수 있으며, 목록의 보존 레이블 영역에 포함된 항목이 아래에 표시됩니다.
4. **모든 위치**에서 위치를 선택하고 폴더 구조를 드릴다운하여 해당 항목까지 이동합니다.
5. 콘텐츠 탐색기에서 기본적으로 항목을 열려면 두 번 클릭을 합니다.

## <a name="see-also"></a>참고 항목

- [민감도 레이블](sensitivity-labels.md)
- [보존 레이블](labels.md)
- [중요한 정보 유형이 찾는 항목](what-the-sensitive-information-types-look-for.md)
- [보존 정책 개요](retention-policies.md)
- [데이터 손실 방지의 개요](data-loss-prevention-policies.md)
