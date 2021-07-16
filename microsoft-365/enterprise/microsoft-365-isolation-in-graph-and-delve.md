---
title: Microsoft 365 Microsoft Graph 테넌트 Delve
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 이 문서에서는 테넌트와 테넌트 Microsoft 365 어떻게 작동하는지 설명을 Office Graph Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464122"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365 Microsoft Graph 테넌트 Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Microsoft 365에서 테넌트 Graph

[Microsoft Graph](https://developer.microsoft.com/graph) 서비스는 Exchange Online, SharePoint Online, Yammer, 비즈니스용 Skype, Azure Active Directory 등을 비롯한 Microsoft 365 서비스 및 기타 Microsoft 서비스 또는 타사 서비스와 같은 외부 서비스에서 활동을 모델화합니다. Microsoft Graph 구성 요소는 전체 Microsoft 365. Microsoft Graph 모음은 콘텐츠 및 활동의 모음과 전체 Office 전체에서 일어나는 관계를 표현합니다. 정교한 기계 학습 기술을 사용하여 관련 콘텐츠, 대화 및 주변 사용자에 연결합니다. 예를 들어 SharePoint Online의 테넌트 인덱스에는 Delve 쿼리를 처리하는 데 사용되는 Microsoft Graph 인덱스가 있으며, SharePoint Online의 분석 처리 엔진은 신호를 저장하고 인사이트를 계산하는 데 사용하며, Exchange Online 각 사용자의 받는 사람 캐시를 테넌트 분석에 입력으로 계산합니다.

Microsoft Graph 개체의 관계 및 상호 작용뿐만 아니라 사용자 및 문서와 같은 엔터프라이즈 개체에 대한 정보도 포함되어 있습니다. 관계 및 상호 작용은 *에지로 표현됩니다.* Microsoft Graph 에지가 동일한 테넌시의 노드 간에만  존재할 수 있는 테넌트별로 분할됩니다. *노드는* URI(Uniform Resource Identifier), 노드 유형, 액세스 제어 목록 및 메타데이터  및 에지가 포함된 얼굴 집합을 포함하는 엔터티입니다. 각 노드에는 공통 지식 모델과 같은  에지와 메타데이터가 연결되어 있습니다. *메타데이터는* Microsoft 365 내에서 검색, 필터링 또는 분석에 사용할 수 있는 노드에 저장된 명명된 Graph. *facet는* 노드에 있는 메타데이터 및 가장자리의 논리적 컬렉션입니다. 각 측면은 노드의 한 측면을 설명합니다. 

Microsoft Graph 모든 데이터를 단일 리포지토리로 가져오지 않습니다. 대신 다른 곳에 있는 데이터에 대한 메타데이터 및 관계가 저장됩니다. Microsoft Graph 여러 데이터 저장소 및 처리 구성 요소로 구성됩니다.

- 테넌트 Graph 저장소는 효율적인 분석을 위해 최적화된 대량 저장소를 제공합니다.
- 활성 콘텐츠 캐시는 사용자 환경을 구동하기 위해 활성 노드 및 에지에 빠르게 임의로 액세스할 수 있도록 합니다.
- 입력 라우터는 테넌트 그래프에 대한 변경 내용의 내부 및 외부를 구성 요소에 고지합니다.

각 워크로드 내의 분석은 테넌트 전체 계산과 관련된 정보를 더한 다음 테넌트 그래프로 푸시합니다. 테넌트의 모든 활동에 대한 테넌트 분석은 동작 패턴에 대한 정보를 생성하기 위한 이유입니다. 예를 들어 Exchange Online 각 사용자의 사서함을 효율적으로 이유 분석하여 각 사용자의 받는 사람 캐시를 계산합니다. 이러한 사용자당 분석은 각 사용자에 *대해 RecipientCache Edge* 집합을 생성하여 테넌트 그래프로 차례로 푸시됩니다. 이렇게 하여 분석 처리를 원본 데이터에 최대한 가깝게 유지할 수 있습니다.

## <a name="tenant-isolation-in-delve"></a>테넌트의 테넌트 Delve

앞서 설명한 Graph Microsoft는 사용자가 엔터프라이즈에서 현재 활동을 검색하고 공동 작업하는 데 도움이 되는 환경을 지원하고, 작업 및 작업 이상에서 콘텐츠 및 활동을 파악하기 위한 엔터티 중심 플랫폼을 Microsoft 365. Delve Microsoft 2013에서 지원되는 첫 번째 환경 Graph.
Delve Microsoft Microsoft 365 통해 Microsoft 365 Yammer Enterprise Microsoft 365 콘텐츠를 Graph 웹 환경입니다. 웹 환경은 데이터를 각각 다른 보드로 표시하고,  각각 특정 항목(예: 주변 추세 또는 수정한 항목)을 *표시합니다.* 각 보드는 문서의 요약 텍스트와 그림을 표시하는 여러 문서 카드로 구성됩니다. 이 카드를 사용하면 사용자가 문서나 문서에 대한 Yammer 같은 작업을 할 수 있습니다. Microsoft 365 테넌트의 각 사용자에 대한 페이지와 해당 사용자와 상호 작용하기 위해 Exchange Online 또는 비즈니스용 Skype 아이콘을 호출할 수 있는 아이콘이 있습니다. 이 Delve Microsoft Graph API를 기반으로 하여 테넌트 기반의 API에 대한 고리로 바인딩됩니다.