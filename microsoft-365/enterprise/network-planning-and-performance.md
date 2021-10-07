---
title: Microsoft 365의 네트워크 계획 및 성능 조정
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/19/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Strat_O365_Enterprise
f1.keywords:
- CSH
search.appverid:
- MET150
ms.assetid: e5f1228c-da3c-4654-bf16-d163daee8848
ms.custom:
- seo-marvel-apr2020
- Adm_O365
description: 이 문서에서는 사용자에 대한 네트워크 대역폭 요구 사항을 계획하고 Microsoft 365 조정하고 문제를 해결하는 데 도움이 됩니다.
ms.openlocfilehash: b48df2c340df38c323c584c6efb3efdc76c26056
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208256"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Microsoft 365의 네트워크 계획 및 성능 조정
처음으로 배포하거나 Microsoft 365 마이그레이션하기 전에 이러한 항목의 정보를 사용하여 필요한 대역폭을 예측한 다음, 배포 또는 마이그레이션할 수 있는 충분한 대역폭이 있는지 테스트하고 확인할 수 Microsoft 365. 개요는 에 대한 네트워크 및 마이그레이션 계획을 [Microsoft 365.](network-and-migration-planning.md)
  
|범주 |설명 |범주 |설명 |
|:-----|:-----|:-----|:-----|
|**네트워크 계획** <br/> ![네트워크.](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |빠른 연결 및 페이지가 빠르게 로드되는 것을 원하나요?  <br/> 에서 최상의 연결 및 성능 [Microsoft 365.](https://aka.ms/o365perfprinciples)<br/>개념을 [Microsoft 365 네트워크 연결 개요를](microsoft-365-networking-overview.md) 참조하세요.<br/> |**네트워크 측정** <br/> ![계산기](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |기본 [Microsoft 365](performance-tuning-using-baselines-and-history.md) 성능 기록 및 성능 문제 해결 계획을 사용하여 성능 조정을 [Microsoft 365.](performance-troubleshooting-plan.md)  <br/> 이러한 도구를 사용하여 [기존 네트워크를 평가합니다.](network-and-migration-planning.md#calculators)  <br/> |
|**모범 사례** <br/> ![모범 사례.](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[에 대한 네트워크](network-and-migration-planning.md#BestPractices)계획 및 마이그레이션 성능을 개선하기 위한 모범 Microsoft 365. 사용자를 바로 지원하기 시작하고 싶나요? 저속 [네트워크에서 Office 365 모범 사례를 참조합니다.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)  <br/> [Microsoft 365 네트워크](./microsoft-365-network-connectivity-principles.md) 연결 원칙은 네트워크 연결을 안전하게 최적화하기 위한 최신 지침을 Microsoft 365 도움이 됩니다.  <br/> |**참조** <br/> ![책 또는 저널](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |IP 주소 및 포트 목록과 같은 세부 정보를 원하나요? 에 [대한 네트워크 계획 참조를 Microsoft 365.](network-and-migration-planning.md#NetReference)  <br/> |
|![Microsoft Cloud Networking for Enterprise Architects 포스터를 참조합니다.](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |네트워크 및 기타 Microsoft 클라우드 플랫폼 및 Microsoft 365 최적화하는 단계는 Microsoft [Cloud Networking for Enterprise Architects](../solutions/cloud-architecture-models.md) 포스터를 참조하세요.  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>성능 조정 및 문제 해결 리소스를 Microsoft 365
<a name="apptuning"> </a>

배포한 Microsoft 365 이 섹션의 항목을 사용하여 성능을 최적화할 수 있습니다. 성능 저하가 발생할 경우 이러한 항목을 사용하여 문제를 해결할 수 있습니다.
  
 **[성능 Office 365](tune-microsoft-365-performance.md)** 조정 : 네트워크 주소 변환과 함께 네트워크 주소 Office 365 자세한 내용은 [NAT support with Office 365.](nat-support-with-microsoft-365.md) 또한 네트워크 연결의 최적화 및 문제 해결을 위한 상위 [10개 Office 365 살펴보세요.](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity) 
  
 **[성능 Exchange Online](tune-exchange-online-performance.md)** 조정: 다음 문서를 사용하여 성능에 대한 Exchange Online 조정합니다. 
  
 **[온라인 비즈니스용 Skype 조정:](tune-skype-for-business-online-performance.md)** 다음 문서를 사용하여 온라인 성능을 비즈니스용 Skype 수 있습니다. 
  
 **[온라인 SharePoint 조정:](tune-sharepoint-online-performance.md)** 다음 문서를 사용하여 온라인 성능을 SharePoint 조정합니다. 
  
 **[성능 Project Online](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)** 조정: 이 문서를 사용하여 성능 Project Online 조정합니다.