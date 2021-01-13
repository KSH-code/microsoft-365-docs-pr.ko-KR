---
title: EDRM을 통해 고급 eDiscovery 맞춤
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365의 Advanced eDiscovery의 기본 제공 워크플로는 EDRM(전자 검색 참조 모델)에 설명된 eDiscovery 프로세스와 일치합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841636"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>전자 검색 참조 모델과 고급 eDiscovery 맞춤

Microsoft 365의 Advanced eDiscovery의 기본 제공 워크플로는 EDRM(전자 검색 참조 모델)에 설명된 eDiscovery 프로세스와 일치합니다.

![EDRM(전자 검색 참조 모델)](../media/EDRMv1.png)

(이미지 원본을 edrm.net. The source image was made available under Creative Commons Attribution 3.0 Unported License.)

고급 eDiscovery가 EDRM 워크플로를 지원하는 방식은 다음과 같습니다.

- **식별.** 조사에 관심이 있는 잠재적 사람을 식별한 후 보유자(데이터 보유자라고도 하는 데이터 보유자)로 추가하여 조사와 관련된 정보를 보유할 수 있습니다. 사용자가 보호자로 추가된 후 쉽게 보존, 수집 및 검토할 수 있습니다.

- **보존.** 고급 eDiscovery를 사용하면 조사와 관련된 데이터를 보존하고 보호할 수 있습니다. 보유하지 않은 데이터를 보류할 수 있습니다. Advanced eDiscovery에는 보유자에 법적 보유 알림을 보내고 확인을 추적할 수 있도록 기본 제공 커뮤니케이션 워크플로도 있습니다.

- **컬렉션입니다.** 조사와 관련된 데이터 원본을 식별하고 보존한 후 Advanced eDiscovery 검색의 기본 제공 검색 도구를 사용하여 해당 사례와 관련이 있을 수 있는 양도 데이터 원본(및 해당되는 경우 비구성 데이터 원본)에서 라이브 데이터를 검색하고 수집할 수 있습니다.

- **처리 중입니다.** 사례와 관련된 모든 데이터를 수집한 후 다음 단계는 추가 검토 및 분석을 위해 처리합니다. Advanced eDiscovery에서 수집 단계에서 식별한 원본 위치 데이터가 Azure Storage 위치(검토 집합이라고도 하여)에 복사되어 사례 데이터의 정적 보기를 제공합니다.  

- **검토합니다.** 검토 집합에 데이터가 추가된 후 특정 문서를 보고 추가 쿼리를 실행하여 사례와 가장 관련된 데이터로 데이터를 줄일 수 있습니다. 또한 특정 문서에 주석을 추가하고 태그를 지정합니다.

- **분석.** Advanced eDiscovery는 조사와 관련이 없다고 판단되는 검토 집합에서 데이터를 더 컬링할 수 있는 통합 분석 도구를 제공합니다. Advance eDiscovery는 관련 데이터의 양을 줄이는 것 외에도 검토 프로세스를 더 쉽고 효율적으로 만들기 위해 콘텐츠를 구성할 수 있도록 하여 법적 검토 비용을 절약할 수 있도록 합니다.

- **프로덕션** 및 **프레젠테이션** 준비가 되면 법적 검토를 위해 검토 집합에서 문서를 내보낼 수 있습니다. 타사 검토 응용 프로그램으로 가져올 수 있도록 문서를 기본 형식 또는 EDRM 지정 형식으로 내보낼 수 있습니다.

## <a name="more-information"></a>추가 정보

Advanced eDiscovery 사용을 시작하고 나서 다음을 참조합니다.

- [Advanced eDiscovery 설정](get-started-with-advanced-ediscovery.md)

- [Advanced eDiscovery 사례 만들기 및 관리](create-and-manage-advanced-ediscoveryv2-case.md)