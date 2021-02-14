---
title: Microsoft Graph 및 Delve의 Microsoft 365 테넌트 고리
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
description: 이 문서에서는 Office Graph 및 Delve에서 Microsoft 365 테넌트가 어떻게 작동하는지 설명을 찾아보는 것이 가장 까다로우며,
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332391"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft Graph 및 Delve의 Microsoft 365 테넌트 고리

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Microsoft Graph에서 테넌트 고리

[Microsoft Graph는](https://developer.microsoft.com/graph) Exchange Online, SharePoint Online, Yammer, 비즈니스용 Skype, Azure Active Directory 등을 비롯한 Microsoft 365 서비스 및 기타 Microsoft 서비스 또는 타사 서비스와 같은 외부 서비스에서 활동을 모델화합니다. Microsoft Graph 구성 요소는 Microsoft 365 전체에서 사용됩니다. Microsoft Graph는 콘텐츠 및 활동의 모음과 전체 Office 제품군에서 발생되는 이러한 활동 간의 관계를 보여줍니다. 정교한 기계 학습 기술을 사용하여 관련 콘텐츠, 대화 및 주변 사용자에 연결합니다. 예를 들어 SharePoint Online의 테넌트 인덱스에는 Delve 쿼리를 처리하는 데 사용되는 Microsoft Graph 인덱스가 있으며, SharePoint Online의 분석 처리 엔진은 신호를 저장하고 인사이트를 계산하는 데 사용하며, Exchange Online은 각 사용자의 받는 사람 캐시를 테넌트 분석에 입력으로 계산합니다.

Microsoft Graph에는 사용자 및 문서와 같은 엔터프라이즈 개체에 대한 정보와 이러한 개체 간의 관계 및 상호 작용에 대한 정보가 포함되어 있습니다. 관계 및 상호 작용은 *에지로 표현됩니다.* Microsoft Graph는 동일한 테넌트의 노드 간에만  에지가 존재할 수 있는 테넌트별로 분할됩니다. *노드는* URI(Uniform Resource Identifier), 노드 유형, 액세스 제어 목록 및 메타데이터와  가장자리를 포함하는 면 집합을 포함하는 엔터티입니다. 각 노드에는 공통 지식 모델과 같은  에지와 관련된 메타데이터 및 에지가 있습니다. *메타데이터는* Microsoft Graph 내에서 검색, 필터링 또는 분석에 사용할 수 있는 노드에 저장된 명명된 속성입니다. *facet는* 노드에 있는 메타데이터 및 가장자리의 논리적 컬렉션입니다. 각 측면은 노드의 한 측면을 설명합니다. 

Microsoft Graph에서는 모든 데이터를 단일 리포지토리로 가져오지 않습니다. 대신 다른 곳에 있는 데이터에 대한 메타데이터 및 관계가 저장됩니다. Microsoft Graph는 다음과 같은 여러 데이터 저장소 및 처리 구성 요소로 구성됩니다.

- 테넌트 그래프 저장소는 효율적인 분석을 위해 최적화된 대량 저장소를 제공합니다.
- 활성 콘텐츠 캐시는 사용자 환경을 구동하기 위해 활성 노드 및 에지에 빠르게 임의로 액세스할 수 있도록 합니다.
- 입력 라우터는 구성 요소에 테넌트 그래프의 변경 내용의 내부 및 외부에 이를 고지합니다.

각 워크로드 내의 분석은 테넌트 전체 계산과 관련된 정보를 디더스하고 테넌트 그래프로 푸시합니다. 테넌트의 모든 활동에 대한 테넌트 분석 이유가 동작 패턴에 대한 인사이트를 생성합니다. 예를 들어 Exchange Online에서는 각 사용자의 사서함에 대해 효율적으로 이유를 분석하여 각 사용자에 대한 받는 사람 캐시를 계산합니다. 이러한 사용자당 분석은 각 사용자에 *대해 RecipientCache Edge* 집합을 생성하여 테넌트 그래프로 차례로 푸시됩니다. 따라서 분석 처리를 원본 데이터에 최대한 가깝게 유지할 수 있습니다.

## <a name="tenant-isolation-in-delve"></a>Delve의 테넌트 고지

앞서 언급했듯이 Microsoft Graph는 사용자가 엔터프라이즈에서 현재 활동을 검색하고 공동으로 작업하는 데 도움이 되는 환경을 제공하며, Microsoft 365 이상에서 콘텐츠 및 활동을 파악하기 위한 분석을 위한 엔터티 중심 플랫폼을 제공합니다. Delve는 Microsoft Graph에서 지원한 첫 번째 환경입니다.
Delve는 Microsoft Graph를 통해 Microsoft 365 및 Yammer Enterprise의 콘텐츠를 Microsoft 365 사용자에게 표시하는 Microsoft 365 웹 환경입니다. 웹 환경은 데이터를 각각 다른 보드로 표시하고,  각각 특정 항목(예: 주변 경향 또는 수정한 항목)을 *표시합니다.* 각 보드는 문서의 요약 텍스트와 그림을 표시하는 여러 문서 카드로 구성됩니다. 이 카드를 사용하면 사용자가 문서나 문서에 대한 문서 Yammer 같은 작업을 할 수 있습니다. Microsoft 365 테넌트의 각 사용자에 대해 이 사용자에 대한 가장 관련성이 높은 문서와 해당 사용자와 상호 작용하기 위해 Exchange Online 또는 비즈니스용 Skype를 호출할 수 있는 아이콘이 있습니다. Delve는 Microsoft Graph API를 기반으로 하기 때문에 해당 API의 테넌트 기반의 고리에 의해 바인딩됩니다.