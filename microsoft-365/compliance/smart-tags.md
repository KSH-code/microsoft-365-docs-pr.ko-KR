---
title: 팜에서 스마트 태그 Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: 스마트 태그를 사용하면 특정 사례에서 콘텐츠를 검토할 때 기계 학습 기능을 Advanced eDiscovery 있습니다. 스마트 태그 그룹을 사용하여 변호사-클라이언트 권한 모델과 같은 기계 학습 검색 모델의 결과를 표시합니다.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218795"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>팜에서 스마트 태그 Advanced eDiscovery

컴퓨터 ML(Advanced eDiscovery) 기능은 검토 집합에서 사례 문서를 검토할 때 의사 결정 프로세스를 보다 효율적으로 만드는 데 도움이 될 수 있습니다. 스마트 태그는 검토 중에 문서에 태그를 지정하는 ML 기록되는 위치로 ML 기능을 가져오는 한 가지 방법입니다. 스마트 태그 그룹을 만들면 스마트 태그 그룹과 연결한 ML 모델의 결과로 결정된 결정이 태그 그룹의 태그와 함께 인라인으로 표시됩니다. 이렇게 하면 특정 문서를 ML 결과 정보를 인라인으로 볼 수 있습니다.

## <a name="how-to-set-up-a-smart-tag-group"></a>스마트 태그 그룹을 설정하는 방법

1. 검토 집합에서 검토 집합 **관리를 클릭한** 다음 태그 **관리를 클릭합니다.**

2. 태그 **그룹 추가를 클릭한** 다음 스마트 태그 **그룹 추가를 선택합니다.**

3. 태그 ML 연결하려는 사용자 지정 모델을 선택합니다.
    
   그러면 태그 그룹과 *N* 자식 태그가 생성됩니다. 여기서 *N은* 모델의 가능한 출력 수입니다. 예를 들어, [변호사-클라이언트](attorney-privilege-detection.md) 권한 검색 모델에는 다음과 같은 두 가지 출력이 있습니다. 

   - **양수** – 변호사-클라이언트 권한이 부여된 콘텐츠가 포함된 문서에 태그를 지정하는 데 사용할 수 있습니다.
   
   - **음수** – 변호사-클라이언트 권한이 부여된 콘텐츠가 없는 문서에 태그를 지정하는 데 사용할 수 있습니다.
    
    이 모델을 선택하면 검토 집합에 대해 두 개의 하위 태그가 있는 태그  **그룹(양수라는** 자식 태그와 네거티브라는 다른 자식 태그)이 만들어집니다. 이 예에서 각 자식 태그는 변호사-클라이언트 권한 검색 모델에서 가능한 출력 중 하나에 해당합니다.

4. 선택적으로 태그 그룹 및 하위 태그의 이름을 다시 지정하면 됩니다. 예를 들어 **Positive** 태그의 이름을 **Privileged로,** **Negative** 태그를 권한 없는 **태그로 이름을 다시 지정합니다.**

## <a name="how-to-use-smart-tags"></a>스마트 태그를 사용하는 방법

문서를 검토할 때 모델의 결과가 해당 자식 태그 옆에 표시됩니다. 예를 들어, 변호사-클라이언트 권한 검색을 위한 스마트 태그 그룹이 있으며 잠재적으로 권한이 부여된 문서를 검토하는 경우 해당 결론의 이유가 해당 태그 옆에 표시됩니다. 태그는 문서에 자동으로 적용되지 않습니다. 검토자에서 문서에 태그를 지정하는 방법을 결정합니다.
