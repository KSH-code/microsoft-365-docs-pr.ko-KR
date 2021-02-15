---
title: Advanced eDiscovery 사례에서 관리
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
ms.assetid: ''
description: Advanced eDiscovery 사례에서 정보 보기, 편집 및 대량 편집에 대해 자세히 알아보고, 정보를 편집하고, 대량으로 편집하는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739871"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Advanced eDiscovery 사례에서 관리

Advanced eDiscovery 사례의  원본 탭에 있는 Custodians 페이지에는 사례에 추가된 모든 상주자 목록이 포함되어 있습니다. 사례에 관리인을 추가하면 각 관리자에 대한 세부 정보가 Azure Active Directory에서 자동으로 수집되며 Advanced eDiscovery에서 볼 수 있습니다.

![Custodians 관리](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>양도자 세부 정보 보기

양도자에 대한 세부 정보를 보려면 Custodians 탭의 목록에서 **custodian을** 클릭합니다. 플라이아웃 페이지가 표시되고 해당 보호자에 대한 다음 정보가 포함되어 있습니다.

- 연락처 정보

  - **표시 이름** - 보금주의 주소부에 표시되는 이름입니다. 일반적으로 이 이름은 양도자 이름, 중간 이니셜 및 성의 조합입니다.
  
   - **메일/SMTP** - 예를 들어, brianj@contoso.onmicrosoft.com. 또한 양도자 UPN(사용자 계정 이름)도 나열됩니다.

  - **title** - 양도자 직위입니다.

  - **Department** - 양도인이 작업하는 부서의 이름입니다.

  - **관리자** - 상사입니다. 지정된 관리자는 이 관리자에 대한 에스컬레이터 통신을 받게됩니다.
  
- 위치 정보

  - **city** - 양도인이 있는 도시입니다.

  - **state** - 양도자 주소의 시 또는 시입니다.

  - **국가/지역** - 양도인이 있는 국가/지역입니다.

  - **Office** - 양도자 장소의 사무실 위치입니다.

- 사례 정보

  - **보류 상태** - 보유자에 대한 보류 상태입니다. 

  - **통신 상태:** 보유자에 대한 보류 알림이 발급된 경우를 나타냅니다. 보호자에 알림이 발행된 경우 이 속성의 이 값은 **게시됩니다.** 양도자에 알림이 발급되지 않은 경우 상태는 **게시되지 않은 상태입니다.** 

  - **status** - 사례 내의 보전자 상태입니다. 활성 **상태는** 양도인이 사례의 일부입니다. 양도인이 사례에서 릴리스된 경우 상태가 릴리스로 **변경됩니다.** 

- 데이터 원본 및 인덱싱 정보

    - **데이터 원본** - 보호자와 연결되어 있으며 사례에 속하는 데이터 원본(사서함, 사이트 및 Teams)의 수와 유형을 보여 주며,

    - **인덱스 업데이트 시간** - 고급 인덱싱 작업이 마지막으로 트리거된 시간 및 날짜를 나타냅니다. 이 속성은 고급 인덱싱 프로세스가 현재 진행 중인 경우도 나타냅니다.


## <a name="edit-a-custodian"></a>양도인 편집

사례가 진행될 때 사례와 관련된 추가 데이터 원본이 있을 수 & 있습니다. 다른 시나리오에서는 검토되고 관련이 없는 것으로 확인된 특정 데이터 원본을 제거할 수 있습니다.

보호자와 연결된 데이터 원본을 업데이트합니다.

1. Advanced  **eDiscovery를 > eDiscovery를 통해 eDiscovery로** 이동한 후 사례를 여는 것이 가장 까다로우며,
  
2. 원본 **탭을** 클릭합니다.
  
3. **Custodians(Custodians)** 페이지에서 목록에서 custodian을 선택하고 플라이아웃 페이지에서 편집을 클릭합니다. 

    ![데이터 원본 편집](../media/EditCustodianDataSource.PNG)
  
4. 데이터 **원본** 선택 탭을 클릭하여 관리인의 Exchange 사서함 및 OneDrive 계정에 대한 설정을 변경하고 데이터 원본 **선택을 클릭합니다.**
  
5. 추가 **데이터** 원본 선택 탭을 클릭하여 거래소와 연결된 Teams, SharePoint 또는 Exchange 사서함을 추가하거나 제거합니다. 

    보호자와 연결된 데이터 원본에 대한 자세한 내용은 사례에 보호자 추가를 [참조하세요.](add-custodians-to-case.md) 
  
6. **보유자에** 대한 보류를 활성화 또는 비활성화하려면 장소 보유를 클릭합니다.

## <a name="re-index-custodian-data"></a>보호자 데이터 다시 인덱싱

법적 조사를 위한 대부분의 eDiscovery 워크플로에서는 법적 사례에 양도인이 추가된 후 보호자 데이터의 하위 집합을 검색합니다. 파일 크기가 매우 크거나 데이터 손상이 있을 수 있기 때문에, 보호자와 연결된 데이터 원본의 일부 항목이 부분적으로 인덱싱될 수 있습니다. Advanced [](indexing-custodian-data.md) eDiscovery의 고급 인덱싱 기능을 사용하여 부분적으로 인덱싱된 항목은 대부분 이러한 항목을 요구 시 다시 인덱싱하여 자동으로 수정될 수 있습니다.

보호자 사례에 추가된 경우, 고급 인덱싱 프로세스에 의해 보호자와 연결된 데이터 원본에 있는 데이터가 자동으로 다시 인덱싱됩니다. 즉, 데이터를 다운로드하여 수정한 다음 오프라인으로 검색하는 대신 데이터를 현재 상태로 두면 됩니다. 그러나 법률 사례의 수명 주기 동안 새 데이터 원본이 보호자와 연결될 수 있습니다. 이 경우 고급 인덱싱 프로세스를 다시 실행하여 부분적으로 인덱싱된 항목을 수정하고 관리자 데이터에 대한 인덱스를 업데이트하여 보호자 데이터를 다시 인덱싱할 수 있습니다.

부분적으로 인덱싱된 항목을 해결하기 위해 다시 인덱싱 프로세스를 트리거합니다.

1. Advanced  **eDiscovery를 > eDiscovery를 통해 eDiscovery로** 이동한 후 사례를 여는 것이 가장 까다로우며,

2. 원본 **탭을** 클릭합니다.

3. **Custodians** 페이지에서 데이터를 다시 인덱서해야 하는 보호자(custodian)를 선택합니다.

4. 플라이아웃 페이지에서 인덱스 **업데이트를 클릭합니다.**

   인덱스 작업이 만들어졌다는 대화 상자가 표시됩니다.

재인덱싱은 장기적인 프로세스입니다. 생성된 해당 작업의 이름은 재인덱싱 보호자 **데이터입니다.** 인덱싱 작업 상태  열의 상태를  모니터링하여 작업 탭 또는 관리 탭에서 진행 상황을 **추적할 수** 있습니다.

자세한 내용은 다음을 참조하세요.

- [오류 처리 작업](processing-data-for-case.md)

- [작업 관리](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>사례에서 양도자 해제

양도인은 사례가 마감되거나, 양도인이 더 이상 사례에 대한 콘텐츠를 보존할 의무가 없는 경우 또는 해당 사례와 더 이상 관련이 없는 것으로 판단되는 경우에 릴리스됩니다. 

보류 알림이 게시된 후 보유자 해제 시, 보유자에 대한 릴리스 알림이 전송됩니다. 또한 보유자와 연결된 데이터 원본에 배치된 보류도 모두 제거됩니다. 법적 보유 알림이 발급되지 않은 자동 보류를 설정한 경우, 릴리스 알림은 전송되지 않지만 해당 보유자에 연결된 데이터 원본에 대한 보류는 제거됩니다.

양도인을 해제합니다. 

1. Advanced  **eDiscovery를 > eDiscovery를 통해 eDiscovery로** 이동한 후 사례를 여는 것이 가장 까다로우며,

2. 원본 **탭을** 클릭합니다.

3. **Custodians** 페이지에서 사례에서 릴리스되는 양도인을 선택합니다.

4. 플라이아웃 페이지에서 **Custodian 릴리스를 클릭합니다.**

   보유자에 연결된 데이터 원본에 보류가 적용되면 보류가 제거되고 다른 Advanced eDiscovery 사례와 연결된 다른 모든 보류가 계속 적용됨을 설명하는 경고 페이지가 표시됩니다. 여기에는 다른 유형의 보존 및 보존 기능(예: Microsoft 365 보존 정책)이 포함됩니다.

5. **예를** 클릭하여 양도인을 해제할지 확인할 수 있습니다. 

    보유자 탭에서 이  사용자의 상태가 릴리스로 설정되어  있으며 플라이아웃 페이지의 보류 상태가 **False로 변경됩니다.**  

> [!NOTE]
> 여러 법적 사건에 양도권이 동시에 관련될 수 있습니다. 보유자도 사례에서 릴리스될 경우 다른 문제의 보류 및 알림은 영향을 하지 않습니다.

## <a name="bulk-edit-custodians"></a>양도자 대량 편집

대량 편집기를 사용하여 동시에 여러 관리인을 편집할 수 있습니다. 이렇게하려면 관리 탭에서 두 개 이상의 관리인을  선택하여 대량 편집기를 표시한 다음 작업 중 하나를 클릭합니다.

![여러 보호자 설정을 편집하는 플라이아웃 페이지](../media/AeDBulkEditCustodians.png)
