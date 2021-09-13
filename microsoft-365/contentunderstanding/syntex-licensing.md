---
title: SharePoint Syntex에 대한 라이선싱
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: SharePoint Syntex 라이선싱에 대해 알아보기
ms.openlocfilehash: 1ab7ab290ca00ba6b47510dfc43f18412b528b0c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210812"
---
# <a name="licensing-for-sharepoint-syntex"></a>SharePoint Syntex에 대한 라이선싱

SharePoint Syntex를 사용하려면 조직에 SharePoint Syntex 구독이 있어야 하고 각 Syntex 사용자에게 라이선스가 있어야 합니다. 나중에 SharePoint Syntex 구독을 취소하거나 평가판이 만료되면 사용자는 더 이상 문서 이해 또는 양식 처리 모델을 생성, 게시 또는 실행할 수 없습니다. 또한 용어 저장소 보고서, SKOS 분류/분류법 가져오기 및 콘텐츠 유형 푸시는 더 이상 사용할 수 없습니다. 모델, 콘텐츠 또는 메타데이터는 삭제되지 않으며 사이트 권한은 변경되지 않습니다.
 
## <a name="tasks-requiring-a-license"></a>라이선스가 필요한 작업
 
다음 작업을 수행하려면 사용자에게 SharePoint Syntex 라이선스가 필요합니다.
 
- 문서 이해 모델을 라이브러리에 적용합니다(라이선스가 없는 사용자는 콘텐츠 센터에 대한 액세스 권한을 부여받을 수 있으며 그곳에서 문서 이해 모델을 만들 수 있지만 문서 라이브러리에 적용할 수는 없습니다)
- 라이브러리의 진입점을 통해 양식 처리 모델 만들기
- 문서 이해 또는 양식 처리 모델이 적용된 라이브러리에 콘텐츠 업로드
- 주문형 문서 이해 모델 실행
- 문서 이해 또는 양식 처리 모델을 사용하여 파일에서 추출한 메타데이터를 봅니다. (사용자는 파일이 이동되는 위치에 관계없이 처리된 파일과 연결된 메타데이터에 액세스하고 사용할 수 있는 라이선스가 있어야 합니다)
- 프리미엄 분류 서비스를 사용합니다. (프리미엄 분류 서비스는 SKOS 기반 용어 집합 가져오기로 구성되며, 엔터프라이즈 콘텐츠 형식을 허브 관련 사이트 및 용어 저장소 보고서에 푸시합니다)

라이선스가 없는 사용자는 콘텐츠 센터에 대한 액세스 권한을 부여받을 수 있으며 그곳에서 문서 이해 모델을 만들 수 있지만 문서 라이브러리에 적용할 수는 없습니다.
 
## <a name="cost-of-running-models"></a>모델 실행 비용
 
문서 이해 모델을 실행하는 비용은 SharePoint Syntex 라이선스 비용에 포함됩니다. 그러나 양식 처리 모델은 학습 및 런타임 처리 모두에 AI Builder 용량을 사용합니다. AI Builder를 사용할 Power Apps 환경에 용량을 할당해야 합니다.
 
조직에 SharePoint Syntex에 대한 SharePoint Syntex 라이선스가 300개 이상 있는 경우 100만 개의 AI Builder 크레딧이 할당됩니다. 최소 300개 라이선스를 유지하면 이 용량이 매월 갱신됩니다. (미사용 크레딧은 매월 이월되지 않습니다) 라이선스가 300개 미만인 경우 양식 처리를 사용하려면 AI Builder 크레딧을 구입해야 합니다.
 
[AI Builder 계산기](https://powerapps.microsoft.com/ai-builder-calculator)을(를) 사용하여 사용자에게 적합한 AI Builder 용량을 추정할 수 있습니다.

사용자 지정 Power Platform 환경을 사용하려면 [해당 환경에 크레딧을 할당](/power-platform/admin/capacity-add-on)해야 합니다.

[Power Platform 관리 센터](https://admin.powerplatform.microsoft.com/resources/capacity)로 이동하여 크레딧 및 사용량을 확인합니다.
  
## <a name="additional-term-store-features"></a>추가 용어 저장소 기능
 
SharePoint Syntex 구독에는 다음과 같은 추가 용어 저장소 기능이 있습니다.
 
- SKOS 기반 용어 집합 가져오기
- 엔터프라이즈 콘텐츠 형식을 허브 사이트로 푸시하면 연결된 사이트와 새로 생성된 목록 또는 라이브러리에도 추가됩니다.
- 테넌트 전반에 걸쳐 게시된 용어 집합 및 사용에 대한 인사이트를 제공하는 용어 저장소 보고서


## <a name="see-also"></a>참고 항목

[Microsoft Power Platform 라이선스 개요](/power-platform/admin/pricing-billing-skus)

[Power Apps 및 Power Automate 라이선싱 FAQ](/power-platform/admin/powerapps-flow-licensing-faq)
