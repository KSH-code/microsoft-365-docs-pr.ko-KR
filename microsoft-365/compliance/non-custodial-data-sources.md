---
title: 고급 eDiscovery 사례에 비보조 데이터 원본 추가
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
description: 고급 eDiscovery 사례에 보유하지 않은 데이터 원본을 추가하고 데이터 원본을 보류할 수 있습니다. 비관리 데이터 원본은 다시 인덱싱되어 부분적으로 인덱싱된 것으로 표시된 모든 콘텐츠는 완전히 신속하게 검색할 수 있도록 다시 처리됩니다.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740355"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>고급 eDiscovery 사례에 비보조 데이터 원본 추가

Advanced eDiscovery의 경우 Microsoft 365 데이터 원본을 해당 사례의 보호자와 연결해야 하는 요구를 항상 충족하지는 않습니다. 하지만 해당 데이터를 검색하고 검토 집합에 추가한 다음 분석 및 검토할 수 있도록 해당 데이터를 사례와 연결해야 할 수 있습니다. Advanced eDiscovery의 기능을  양도하지 않는 데이터 원본이라고 하여, 이를 보호자에 연결하지 않고도 사례에 데이터를 추가할 수 있습니다. 또한 보호자와 연결된 데이터에 사용할 수 있는 비보조 데이터에 동일한 Advanced eDiscovery 기능을 적용합니다. 보유하지 않은 데이터에 적용할 수 있는 가장 유용한 두 가지는 보유한 후 고급 인덱싱을 사용하여 처리하는 [것입니다.](indexing-custodian-data.md)

## <a name="add-a-non-custodial-data-source"></a>비보조 데이터 원본 추가

고급 eDiscovery 사례에서 비관리 데이터 원본을 추가하고 관리하기 위해 다음 단계를 수행합니다.

1. Advanced **eDiscovery** 홈 페이지에서 데이터를 추가할 사례를 클릭합니다.

2. 데이터 원본 **탭을 클릭한** 다음 데이터 원본 추가 데이터 **위치**  >  **추가를 클릭합니다.**

3. 새 **비보조** 데이터 위치 플라이아웃 페이지에서 사례에 추가할 데이터 원본을 선택합니다. **SharePoint** 또는 **Exchange** 섹션을 확장한 다음 편집을 클릭하여 여러 사서함과 사이트를 추가할 **수 있습니다.**

   ![SharePoint 사이트 및 Exchange 사서함을 비소유 데이터 원본으로 추가](../media/NonCustodialDataSources1.png)

   - **SharePoint** - **편집을** 클릭하여 사이트를 추가합니다. 목록에서 사이트를 선택하거나 검색 표시줄에 사이트의 URL을 입력하여 사이트를 검색할 수 있습니다. 비구조 데이터 원본으로 추가할 사이트를 선택하고 추가를 **클릭합니다.**

   - **Exchange** - **편집을** 클릭하여 사서함을 추가합니다. 사서함 또는 메일 그룹의 검색 상자에 이름 또는 별칭(최소 3자)을 입력합니다. 비보안 데이터 원본으로 추가할 사서함을 선택하고 추가를 **클릭합니다.**

   > [!NOTE]
   > **SharePoint** 및 **Exchange** 섹션을 사용하여 팀 또는 Yammer 그룹과 연결된 사이트 및 사서함을 비구성 데이터 원본으로 추가할 수 있습니다. 팀 또는 그룹과 연결된 사서함 및 사이트를 별도로 Yammer 합니다.

4. 보유하지 않은 데이터 원본을 추가한 후 해당 위치를 보류할지 아니면 보류할지 선택할 수 있습니다. 데이터 원본 옆의  보류 확인란을 선택하거나 선택하지 않은 경우 보류합니다.

5. 새 **비보조** 데이터  위치 플라이아웃 페이지의 아래쪽에 추가를 클릭하여 데이터 원본을 사례에 추가합니다.

   추가한 각 비영구 데이터 원본이 데이터 원본 페이지에 **나열됩니다.** 비보조 데이터 원본은 원본 형식 열의 데이터 위치 값으로 **식별됩니다.** 

   ![데이터 원본 탭의 비보조 데이터 원본](../media/NonCustodialDataSources2.png)

해당 사례에 비영구 데이터 원본을 추가하고 나면 해당 사례의 작업 탭에 비보조 데이터 *Reindexing이라는* 작업이 만들어지며 표시됩니다.  작업을 만든 후 고급 인덱싱 프로세스가 시작된 후 데이터 원본을 다시 인덱싱합니다.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>보유하지 않은 데이터 원본에 대한 보류 관리

보유하지 않은 데이터 원본에 대해 보류를 설정하면 해당 사례에 대한 보유하지 않은 데이터 원본을 포함하는 보류 정책이 자동으로 만들어집니다. 다른 보유되지 않은 데이터 원본을 보류하면 해당 데이터 원본이 이 보류 정책에 추가됩니다.

1. Advanced eDiscovery 사례를 열고 보류 **탭을** 선택합니다.

2. **NCDSHold-를 \<GUID\>** 클릭합니다. 여기서 GUID 값은 사례에 고유합니다.

   플라이아웃 페이지에는 보유 중이 아닌 데이터 원본에 대한 정보 및 통계가 표시됩니다.

   ![보유하지 않은 데이터 원본에 대한 플라이아웃 페이지에 통계가 표시됩니다.](../media/NonCustodialDataSourcesHoldFlyout.png)

3. 보류 **편집을** 클릭하여 보유되지 않은 데이터 원본을 보고 다음 관리 작업을 수행합니다.

   - 위치 **페이지에서** 보류에서 비보류 데이터 원본을 제거하여 해제할 수 있습니다. 데이터 원본을 공개해도 해당 사례에서 비보조 데이터 원본은 제거되지 않습니다. 데이터 원본에 배치된 보류만 제거합니다.

   - 쿼리 **페이지에서** 보류를 편집하여 모든 보유가 아닌 모든 데이터 원본에 적용되는 쿼리 기반 보류를 만들 수 있습니다.
