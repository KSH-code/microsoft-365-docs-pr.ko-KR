---
title: Microsoft 365의 네트워크 계획 및 성능 조정
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/19/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_Enterprise
f1.keywords:
- CSH
search.appverid:
- MET150
ms.assetid: e5f1228c-da3c-4654-bf16-d163daee8848
ms.custom:
- seo-marvel-apr2020
- Adm_O365
description: 이 문서는 Microsoft 365에 대한 네트워크 대역폭 요구 사항을 계획하고 성능을 미세 조정하고 문제를 해결하는 데 도움이 됩니다.
ms.openlocfilehash: bf05e4128f8ba5ddecce76cb00dc945f43c9c59a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923603"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Microsoft 365의 네트워크 계획 및 성능 조정
Microsoft 365로 처음 배포하거나 Microsoft 365로 마이그레이션하기 전에 이러한 항목의 정보를 사용하여 필요한 대역폭을 예측한 다음 Microsoft 365로 배포하거나 마이그레이션하기에 충분한 대역폭이 있는지 테스트하고 확인할 수 있습니다. 개요는 Microsoft [365에 대한 네트워크](network-and-migration-planning.md)및 마이그레이션 계획을 참조하세요.
  
|||||
|:-----|:-----|:-----|:-----|
|**네트워크 계획** <br/> ![네트워크](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |빠른 연결 및 페이지가 빠르게 로드되는 것을 원하나요?  <br/> Microsoft 365에서 최상의 연결 및 성능 [다운로드를 읽어 읽습니다.](https://aka.ms/o365perfprinciples)<br/>개념을 이해하기 위해 [Microsoft 365 네트워크 연결](microsoft-365-networking-overview.md) 개요를 읽어 읽습니다.<br/> |**네트워크 측정** <br/> ![계산기](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |Microsoft [365에](performance-tuning-using-baselines-and-history.md) 대한 기준 및 성능 기록 및 성능 문제 해결 계획을 사용하여 [Microsoft 365 성능 조정을 읽어 읽습니다.](performance-troubleshooting-plan.md)  <br/> 이러한 도구를 사용하여 [기존 네트워크를 평가합니다.](network-and-migration-planning.md#calculators)  <br/> |
|**모범 사례** <br/> ![모범 사례](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[Microsoft 365의 네트워크](network-and-migration-planning.md#BestPractices)계획 및 마이그레이션 성능 개선을 위한 모범 사례 사용자를 바로 지원하기 시작하고 싶나요? 저속 [네트워크에서 Office 365를](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)사용하는 모범 사례를 참조합니다.  <br/> [Microsoft 365 네트워크](./microsoft-365-network-connectivity-principles.md) 연결 원칙은 Microsoft 365 네트워크 연결을 안전하게 최적화하기 위한 최신 지침을 이해하는 데 도움이 됩니다.  <br/> |**참조** <br/> ![책 또는 저널](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |IP 주소 및 포트 목록과 같은 세부 정보를 원하나요? Microsoft [365에 대한 네트워크 계획 참조를 참조합니다.](network-and-migration-planning.md#NetReference)  <br/> |
|![Microsoft Cloud Networking for Enterprise Architects 포스터 참조](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |Microsoft 365 및 기타 Microsoft 클라우드 플랫폼 및 서비스에 맞게 네트워크를 최적화하는 단계는 [Microsoft Cloud Networking for Enterprise Architects 포스터를 참조하세요.](../solutions/cloud-architecture-models.md)  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>Microsoft 365의 성능 조정 및 문제 해결 리소스
<a name="apptuning"> </a>

Microsoft 365를 배포한 후 이 섹션의 항목을 사용하여 성능을 최적화할 수 있습니다. 성능 저하가 발생할 경우 이러한 항목을 사용하여 문제를 해결할 수 있습니다.
  
 **[Office 365 성능](tune-microsoft-365-performance.md)** 조정 : Office 365에서 네트워크 주소 변환을 사용하는 데 대한 자세한 내용은 [NAT support with Office 365을 참조하세요.](nat-support-with-microsoft-365.md) 또한 Office 365 네트워크 연결 최적화 및 문제 해결을 위한 [상위 10개 팁을 살펴보세요.](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity) 
  
 **[Exchange Online 성능 조정:](tune-exchange-online-performance.md)** 다음 문서를 사용하여 Exchange Online 성능을 미세 조정합니다. 
  
 **[비즈니스용 Skype Online 성능](tune-skype-for-business-online-performance.md)** 조정: 다음 문서를 사용하여 비즈니스용 Skype Online 성능을 미세 조정할 수 있습니다. 
  
 **[SharePoint Online 성능 조정:](tune-sharepoint-online-performance.md)** 다음 문서를 사용하여 SharePoint Online 성능을 미세 조정할 수 있습니다. 
  
 **[Project Online 성능 조정:](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)** 이 문서를 사용하여 Project Online 성능을 미세 조정할 수 있습니다.